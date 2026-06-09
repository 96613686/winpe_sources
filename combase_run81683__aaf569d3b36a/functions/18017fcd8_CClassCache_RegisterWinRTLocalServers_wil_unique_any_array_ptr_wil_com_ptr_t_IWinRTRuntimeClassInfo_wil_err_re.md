# CClassCache::RegisterWinRTLocalServers(wil::unique_any_array_ptr<wil::com_ptr_t<IWinRTRuntimeClassInfo,wil::err_returncode_policy>,wil::process_heap_deleter,com_ptr_deleter,unsigned __int64> &,long (**)(HSTRING__ *,IActivationFactory * *),uint,_RO_REGISTRATION_COOKIE * *)

- ea: `0x18017fcd8`
- end: `0x18018028a`
- name: `?RegisterWinRTLocalServers@CClassCache@@SAJAEAV?$unique_any_array_ptr@V?$com_ptr_t@UIWinRTRuntimeClassInfo@@Uerr_returncode_policy@wil@@@wil@@Uprocess_heap_deleter@2@Ucom_ptr_deleter@@_K@wil@@PEAP6AJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@ZIPEAPEAU_RO_REGISTRATION_COOKIE@@@Z`
- size: `1458`
- prototype: `HRESULT __fastcall(wil::unique_any_array_ptr<wil::com_ptr_t<IWinRTRuntimeClassInfo,wil::err_returncode_policy>,wil::process_heap_deleter,com_ptr_deleter,unsigned __int64> *activatableClassInfos, HRESULT (__fastcall **activationFactoryCallbacks)(HSTRING__ *, IActivationFactory **), unsigned int count, _RO_REGISTRATION_COOKIE **cookie)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18017fc7c`

## callees

- `0x18000b408`
- `0x18002a3ec`
- `0x18002d330`
- `0x18002e040`
- `0x18002f1b0`
- `0x18002f9a0`
- `0x18003a8bc`
- `0x1800450a0`
- `0x180058130`
- `0x18006c1d0`
- `0x1800c4250`
- `0x1800def90`
- `0x1801003b8`
- `0x180105a24`
- `0x18012cf5c`
- `0x1801314f8`
- `0x18014602c`
- `0x18017fcd8`
- `0x18019a654`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017fd27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017fd27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18017ffa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801801e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801801fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18017ffa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801801e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801801fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18017fd16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18017ff98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18017fd16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18017ff98`

## string_xrefs

- `0x18017feba`: `onecore\com\combase\ih\hash.hxx`

## pseudocode

```c

```
