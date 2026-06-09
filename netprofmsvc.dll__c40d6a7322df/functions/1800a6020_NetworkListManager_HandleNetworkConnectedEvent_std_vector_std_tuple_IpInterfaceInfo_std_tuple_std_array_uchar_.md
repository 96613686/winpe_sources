# NetworkListManager::HandleNetworkConnectedEvent(std::vector<std::tuple<IpInterfaceInfo,std::tuple<std::array<uchar,48>,NlmSignatures::SignatureSources>,NlmDomain::AuthenticationState,PerInterfaceData>,std::allocator<std::tuple<IpInterfaceInfo,std::tuple<std::array<uchar,48>,NlmSignatures::SignatureSources>,NlmDomain::AuthenticationState,PerInterfaceData>>> const &,tagNLA_SIGNATURE *,ulong,_GUID const *,INTERFACE_DATA const *,ulong,wchar_t const *,wchar_t const *,SIGNATURE_EX_DATA *)

- ea: `0x1800a6020`
- end: `0x1800a6ebb`
- name: `?HandleNetworkConnectedEvent@NetworkListManager@@AEAA_NAEBV?$vector@V?$tuple@UIpInterfaceInfo@@V?$tuple@V?$array@E$0DA@@std@@W4SignatureSources@NlmSignatures@@@std@@UAuthenticationState@NlmDomain@@UPerInterfaceData@@@std@@V?$allocator@V?$tuple@UIpInterfaceInfo@@V?$tuple@V?$array@E$0DA@@std@@W4SignatureSources@NlmSignatures@@@std@@UAuthenticationState@NlmDomain@@UPerInterfaceData@@@std@@@2@@std@@PEAUtagNLA_SIGNATURE@@KPEBU_GUID@@PEBUINTERFACE_DATA@@KPEB_W4PEAUSIGNATURE_EX_DATA@@@Z`
- size: `3739`
- prototype: `char __fastcall(NetworkListManager *, __int64 *, __int64, unsigned int, struct _GUID *, struct INTERFACE_DATA *, unsigned int, wchar_t *, wchar_t *, struct SIGNATURE_EX_DATA *)`
- caller_count: `1`
- callee_count: `37`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800a59c4`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180013470`
- `0x180014fb0`
- `0x180015608`
- `0x180015650`
- `0x180018968`
- `0x180018c2c`
- `0x180019274`
- `0x180019a48`
- `0x18001a3cc`
- `0x18001e8e0`
- `0x18001f640`
- `0x180023358`
- `0x18002bd40`
- `0x180034c24`
- `0x180037210`
- `0x1800386bc`
- `0x180038878`
- `0x1800460dc`
- `0x18005a9b8`
- `0x18006d36c`
- `0x180073420`
- `0x1800957bc`
- `0x18009ddd4`
- `0x1800a6020`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800ab204`
- `0x1800bf090`
- `0x1800c6864`
- `0x1800c86bc`
- `0x1800ca138`
- `0x1800ca3bc`
- `0x1800cafd0`
- `0x1800cfea4`
- `0x180136d80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6818`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6818`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a654f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a6672`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a654f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a6672`

## string_xrefs

- `0x1800a6560`: `onecore\net\netprofiles\service\src\host\lib\profmani.cpp`
- `0x1800a6683`: `onecore\net\netprofiles\service\src\host\lib\profmani.cpp`

## pseudocode

```c

```
