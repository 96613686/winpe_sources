# DsrGetDcNameEx2

- ea: `0x180004420`
- end: `0x180004a4e`
- name: `DsrGetDcNameEx2`
- size: `1582`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, struct _GUID *, unsigned __int16 *, unsigned int, struct _DOMAIN_CONTROLLER_INFOW **)`
- caller_count: `11`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x180017074`
- `0x18001c824`
- `0x18002a360`
- `0x180031a60`
- `0x180031aa0`
- `0x1800378d4`
- `0x180060fa4`
- `0x180061a74`
- `0x180062d04`
- `0x180062ee0`
- `0x1800746dc`

## callees

- `0x180003220`
- `0x180004420`
- `0x180007278`
- `0x18000bd98`
- `0x18000d094`
- `0x18000e270`
- `0x18000ed34`
- `0x180019894`
- `0x18001ef7c`
- `0x1800208ac`
- `0x180024adc`
- `0x180025708`
- `0x18002601c`
- `0x18002af18`
- `0x18002bd1c`
- `0x180040f0c`
- `0x180045678`
- `0x1800788c0`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000486d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000486d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800047ec`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800047ec`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180004524`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180004524`
- `ntdll!RtlLeaveCriticalSection` at `0x1800044b1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800044c7`
- `ntdll!RtlLeaveCriticalSection` at `0x180004624`
- `ntdll!RtlLeaveCriticalSection` at `0x180004641`
- `ntdll!RtlLeaveCriticalSection` at `0x1800046b4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000489c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800044b1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800044c7`
- `ntdll!RtlLeaveCriticalSection` at `0x180004624`
- `ntdll!RtlLeaveCriticalSection` at `0x180004641`
- `ntdll!RtlLeaveCriticalSection` at `0x1800046b4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000489c`
- `ntdll!RtlEnterCriticalSection` at `0x18000449b`
- `ntdll!RtlEnterCriticalSection` at `0x180004604`
- `ntdll!RtlEnterCriticalSection` at `0x18000472d`
- `ntdll!RtlEnterCriticalSection` at `0x18000449b`
- `ntdll!RtlEnterCriticalSection` at `0x180004604`
- `ntdll!RtlEnterCriticalSection` at `0x18000472d`
- `netutils!NetApiBufferFree` at `0x1800049ea`
- `netutils!NetApiBufferFree` at `0x1800049f3`
- `netutils!NetApiBufferFree` at `0x1800049ea`
- `netutils!NetApiBufferFree` at `0x1800049f3`
- `netutils!NetpwNameValidate` at `0x180004815`
- `netutils!NetpwNameValidate` at `0x180004815`

## string_xrefs

- `0x180004763`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`

## pseudocode

```c

```
