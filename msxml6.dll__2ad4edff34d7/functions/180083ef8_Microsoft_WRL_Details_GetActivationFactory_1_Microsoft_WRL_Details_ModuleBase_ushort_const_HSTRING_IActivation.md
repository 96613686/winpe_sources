# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180083ef8`
- end: `0x180084068`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, const wchar_t *activatibleClassId, HSTRING__ *ppFactory, IActivationFactory **modulePtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009a700`

## callees

- `0x180083ef8`
- `0x180084070`
- `0x1800cada0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180083f32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180083f32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180083f48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180083f48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083f66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180083f66`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18008403f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18008403f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180084000`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180084000`

## string_xrefs

- `0x180084008`: `activatibleClassId`

## pseudocode

```c

```
