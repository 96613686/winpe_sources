# JsonPushBackMbcs(JsonBuilder &,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<char,utl::char_traits<char>> const &,uint,uint)

- ea: `0x1800447a8`
- end: `0x180044b8e`
- name: `?JsonPushBackMbcs@@YAKAEAVJsonBuilder@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEBV?$basic_string_view@DU?$char_traits@D@utl@@@4@II@Z`
- size: `998`
- prototype: `__int64 __usercall@<rax>(JsonBuilder *this@<rcx>, UINT CodePage, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1801e37f4`

## callees

- `0x1800409a4`
- `0x1800409f0`
- `0x180043360`
- `0x1800447a8`
- `0x18020baa0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180044a56`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180044ac3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180044b7d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180044a56`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180044ac3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180044b7d`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x180044ab5`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x180044ab5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044aa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044aa7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044a8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044a8a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180044aff`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180044aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004495e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004495e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180044804`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180044948`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180044804`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180044948`

## string_xrefs

- `0x180044a4f`: `JsonBuilder - cchName too large`
- `0x180044abc`: `JsonBuilder - too much data`
- `0x180044b76`: `JsonBuilder - cbValue too large`

## pseudocode

```c

```
