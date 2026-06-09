# GetFileNameComponentOfModulePath<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18003c810`
- end: `0x18003ca03`
- name: `??$GetFileNameComponentOfModulePath@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@@YAJPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `499`
- prototype: `HRESULT __fastcall(HINSTANCE__ *module, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *fileNamePartOfPath)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ea60`
- `0x18000ee90`
- `0x18003ac00`
- `0x180114a34`
- `0x180114b74`

## callees

- `0x18000df0c`
- `0x18003a8bc`
- `0x18003c608`
- `0x18003c810`
- `0x1800bc1c8`
- `0x1800bdc04`
- `0x180179024`
- `0x18019a5ea`
- `0x18019a654`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003c9cc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003c9cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c895`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c895`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c9a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c9a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c912`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c956`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c992`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c912`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c956`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c992`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003c84f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003c84f`

## string_xrefs

- `0x18003c944`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003c8eb`: `onecore\com\combase\inc\ModuleInfo.hpp`
- `0x18003c974`: `onecore\com\combase\inc\ModuleInfo.hpp`

## pseudocode

```c

```
