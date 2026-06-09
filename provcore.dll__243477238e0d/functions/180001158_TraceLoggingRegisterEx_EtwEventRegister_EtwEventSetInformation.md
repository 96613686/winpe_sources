# TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation

- ea: `0x180001158`
- end: `0x1800011ff`
- name: `TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation`
- size: `167`
- prototype: `HRESULT __fastcall(const _tlgProvider_t *hProvider, void (__fastcall *pEnableCallback)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *), void *pCallbackContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180022664`

## callees

- `0x180001158`
- `0x180002790`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x1800011b4`
- `ntdll!EtwEventRegister` at `0x1800011b4`
- `ntdll!EtwEventSetInformation` at `0x1800011e4`
- `ntdll!EtwEventSetInformation` at `0x1800011e4`

## pseudocode

```c

```
