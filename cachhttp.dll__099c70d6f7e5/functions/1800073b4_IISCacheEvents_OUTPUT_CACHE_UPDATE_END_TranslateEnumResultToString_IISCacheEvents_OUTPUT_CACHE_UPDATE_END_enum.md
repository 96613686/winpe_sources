# IISCacheEvents::OUTPUT_CACHE_UPDATE_END::TranslateEnumResultToString(IISCacheEvents::OUTPUT_CACHE_UPDATE_END::enumResult)

- ea: `0x1800073b4`
- end: `0x180007461`
- name: `?TranslateEnumResultToString@OUTPUT_CACHE_UPDATE_END@IISCacheEvents@@SAPEBGW4enumResult@12@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180007080`

## callees

- `0x1800073b4`

## string_xrefs

- `0x180007449`: `CACHE_FULL`
- `0x180007431`: `ALREADY_CACHED`

## pseudocode

```c
const wchar_t *__fastcall IISCacheEvents::OUTPUT_CACHE_UPDATE_END::TranslateEnumResultToString(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx

  if ( a1 <= 6 )
  {
    if ( a1 == 6 )
      return L"STATUS_NOT_OK";
    if ( !a1 )
      return L"ADDED";
    v1 = a1 - 1;
    if ( !v1 )
      return L"UNKNOWN_ERROR";
    v2 = v1 - 1;
    if ( !v2 )
      return L"NOT_FREQUENTLY_HIT";
    v3 = v2 - 1;
    if ( !v3 )
      return L"HEADERS_FLUSHED";
    v4 = v3 - 1;
    if ( !v4 )
      return L"HEADERS_SUPPRESSED";
    if ( v4 == 1 )
      return L"VERB_NOT_GET";
    return 0;
  }
  v6 = a1 - 7;
  if ( !v6 )
    return L"CACHING_DISABLED";
  v7 = v6 - 1;
  if ( !v7 )
    return L"RESPONSE_TOO_BIG";
  v8 = v7 - 1;
  if ( !v8 )
    return L"CACHE_FULL";
  v9 = v8 - 1;
  if ( !v9 )
    return L"VARY_BY_NOT_MATCH";
  v10 = v9 - 1;
  if ( !v10 )
    return L"ENTRY_EXISTS";
  if ( v10 != 1 )
    return 0;
  return L"ALREADY_CACHED";
}

```

## disassembly

```asm
0x1800073b4  cmp     ecx, 6
0x1800073b7  ja      short loc_180007410
0x1800073b9  jz      short loc_180007408
0x1800073bb  test    ecx, ecx
0x1800073bd  jz      short loc_180007400
0x1800073bf  sub     ecx, 1
0x1800073c2  jz      short loc_1800073F8
0x1800073c4  sub     ecx, 1
0x1800073c7  jz      short loc_1800073F0
0x1800073c9  sub     ecx, 1
0x1800073cc  jz      short loc_1800073E8
0x1800073ce  sub     ecx, 1
0x1800073d1  jz      short loc_1800073E0
0x1800073d3  cmp     ecx, 1
0x1800073d6  jnz     short loc_18000742E
0x1800073d8  lea     rax, aVerbNotGet; "VERB_NOT_GET"
0x1800073df  retn
0x1800073e0  lea     rax, aHeadersSuppres; "HEADERS_SUPPRESSED"
0x1800073e7  retn
0x1800073e8  lea     rax, aHeadersFlushed; "HEADERS_FLUSHED"
0x1800073ef  retn
0x1800073f0  lea     rax, aNotFrequentlyH; "NOT_FREQUENTLY_HIT"
0x1800073f7  retn
0x1800073f8  lea     rax, aUnknownError; "UNKNOWN_ERROR"
0x1800073ff  retn
0x180007400  lea     rax, aAdded; "ADDED"
0x180007407  retn
0x180007408  lea     rax, aStatusNotOk; "STATUS_NOT_OK"
0x18000740f  retn
0x180007410  sub     ecx, 7
0x180007413  jz      short loc_180007459
0x180007415  sub     ecx, 1
0x180007418  jz      short loc_180007451
0x18000741a  sub     ecx, 1
0x18000741d  jz      short loc_180007449
0x18000741f  sub     ecx, 1
0x180007422  jz      short loc_180007441
0x180007424  sub     ecx, 1
0x180007427  jz      short loc_180007439
0x180007429  cmp     ecx, 1
0x18000742c  jz      short loc_180007431
0x18000742e  xor     eax, eax
0x180007430  retn
0x180007431  lea     rax, aAlreadyCached; "ALREADY_CACHED"
0x180007438  retn
0x180007439  lea     rax, aEntryExists; "ENTRY_EXISTS"
0x180007440  retn
0x180007441  lea     rax, aVaryByNotMatch; "VARY_BY_NOT_MATCH"
0x180007448  retn
0x180007449  lea     rax, aCacheFull; "CACHE_FULL"
0x180007450  retn
0x180007451  lea     rax, aResponseTooBig; "RESPONSE_TOO_BIG"
0x180007458  retn
0x180007459  lea     rax, aCachingDisable; "CACHING_DISABLED"
0x180007460  retn
```
