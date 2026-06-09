# IISCacheEvents::HTTPSYS_CACHEABLE::TranslateEnumReasonToString(IISCacheEvents::HTTPSYS_CACHEABLE::enumReason)

- ea: `0x18002639c`
- end: `0x180026506`
- name: `?TranslateEnumReasonToString@HTTPSYS_CACHEABLE@IISCacheEvents@@SAPEBGW4enumReason@12@@Z`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800256ec`

## callees

- `0x18002639c`

## string_xrefs

- `0x1800263eb`: `HTTPSYS_CACHE_DISABLED`
- `0x1800263e3`: `FILE_COMPRESSIBLE`
- `0x18002643d`: `FILTER_CACHE_UNAWARE`
- `0x180026435`: `NON_ANONYMOUS_ACCESS`
- `0x180026492`: `FILE_NOT_CACHED`
- `0x1800264ba`: `DYNAMIC_COMPRESSION_ENABLED`
- `0x1800264ee`: `NO_CACHE_INVALIDATOR`

## pseudocode

```c
const wchar_t *__fastcall IISCacheEvents::HTTPSYS_CACHEABLE::TranslateEnumReasonToString(unsigned int a1)
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
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx

  if ( a1 <= 0xD )
  {
    if ( a1 == 13 )
      return L"CUSTOM_LOGGING";
    if ( a1 > 6 )
    {
      v6 = a1 - 7;
      if ( !v6 )
        return L"HTTP_STATUS_NOT_OK";
      v7 = v6 - 1;
      if ( !v7 )
        return L"CHILD_REQUEST";
      v8 = v7 - 1;
      if ( !v8 )
        return L"HANDLER_HTTPSYS_UNFRIENDLY";
      v9 = v8 - 1;
      if ( !v9 )
        return L"FILTER_CACHE_UNAWARE";
      v10 = v9 - 1;
      if ( !v10 )
        return L"NON_ANONYMOUS_ACCESS";
      if ( v10 == 1 )
        return L"IP_RESTRICTION_SET";
    }
    else
    {
      if ( a1 == 6 )
        return L"URL_CHANGE_BY_FILTER";
      if ( !a1 )
        return L"OK";
      v1 = a1 - 1;
      if ( !v1 )
        return L"NO_METADATA";
      v2 = v1 - 1;
      if ( !v2 )
        return L"HTTPSYS_CACHE_DISABLED";
      v3 = v2 - 1;
      if ( !v3 )
        return L"FILE_COMPRESSIBLE";
      v4 = v3 - 1;
      if ( !v4 )
        return L"FOOTER_ENABLED";
      if ( v4 == 1 )
        return L"SUPRESSING_ENTITY";
    }
    return 0;
  }
  if ( a1 <= 0x14 )
  {
    if ( a1 == 20 )
      return L"DYNAMIC_COMPRESSION_ENABLED";
    v11 = a1 - 14;
    if ( !v11 )
      return L"SSL_RESTRICTION";
    v12 = v11 - 1;
    if ( !v12 )
      return L"ISAPI_NOT_CACHING";
    v13 = v12 - 1;
    if ( !v13 )
      return L"STATIC_REQUEST_QUERYSTRING";
    v14 = v13 - 1;
    if ( !v14 )
      return L"RESPONSE_MORE_DATA";
    v15 = v14 - 1;
    if ( !v15 )
      return L"FILE_NOT_CACHED";
    if ( v15 == 1 )
      return L"RESPONSE_SENDING_RAW_HEADERS";
    return 0;
  }
  v16 = a1 - 21;
  if ( !v16 )
    return L"NO_PIPELINE_ENABLE";
  v17 = v16 - 1;
  if ( !v17 )
    return L"VERB_NOT_GET";
  v18 = v17 - 1;
  if ( !v18 )
    return L"NO_CACHE_INVALIDATOR";
  v19 = v18 - 1;
  if ( !v19 )
    return L"HANDLER_CHANGED";
  if ( v19 != 1 )
    return 0;
  return L"REQUEST_FILTER_RULE";
}

```

## disassembly

```asm
0x18002639c  cmp     ecx, 0Dh
0x18002639f  ja      loc_180026465
0x1800263a5  jz      loc_18002645D
0x1800263ab  cmp     ecx, 6
0x1800263ae  ja      short loc_18002640B
0x1800263b0  jz      short loc_180026403
0x1800263b2  test    ecx, ecx
0x1800263b4  jz      short loc_1800263FB
0x1800263b6  sub     ecx, 1
0x1800263b9  jz      short loc_1800263F3
0x1800263bb  sub     ecx, 1
0x1800263be  jz      short loc_1800263EB
0x1800263c0  sub     ecx, 1
0x1800263c3  jz      short loc_1800263E3
0x1800263c5  sub     ecx, 1
0x1800263c8  jz      short loc_1800263DB
0x1800263ca  cmp     ecx, 1
0x1800263cd  jnz     loc_1800264DB
0x1800263d3  lea     rax, aSupressingEnti; "SUPRESSING_ENTITY"
0x1800263da  retn
0x1800263db  lea     rax, aFooterEnabled; "FOOTER_ENABLED"
0x1800263e2  retn
0x1800263e3  lea     rax, aFileCompressib; "FILE_COMPRESSIBLE"
0x1800263ea  retn
0x1800263eb  lea     rax, aHttpsysCacheDi; "HTTPSYS_CACHE_DISABLED"
0x1800263f2  retn
0x1800263f3  lea     rax, aNoMetadata; "NO_METADATA"
0x1800263fa  retn
0x1800263fb  lea     rax, aOk_0; "OK"
0x180026402  retn
0x180026403  lea     rax, aUrlChangeByFil; "URL_CHANGE_BY_FILTER"
0x18002640a  retn
0x18002640b  sub     ecx, 7
0x18002640e  jz      short loc_180026455
0x180026410  sub     ecx, 1
0x180026413  jz      short loc_18002644D
0x180026415  sub     ecx, 1
0x180026418  jz      short loc_180026445
0x18002641a  sub     ecx, 1
0x18002641d  jz      short loc_18002643D
0x18002641f  sub     ecx, 1
0x180026422  jz      short loc_180026435
0x180026424  cmp     ecx, 1
0x180026427  jnz     loc_1800264DB
0x18002642d  lea     rax, aIpRestrictionS; "IP_RESTRICTION_SET"
0x180026434  retn
0x180026435  lea     rax, aNonAnonymousAc; "NON_ANONYMOUS_ACCESS"
0x18002643c  retn
0x18002643d  lea     rax, aFilterCacheUna; "FILTER_CACHE_UNAWARE"
0x180026444  retn
0x180026445  lea     rax, aHandlerHttpsys; "HANDLER_HTTPSYS_UNFRIENDLY"
0x18002644c  retn
0x18002644d  lea     rax, aChildRequest; "CHILD_REQUEST"
0x180026454  retn
0x180026455  lea     rax, aHttpStatusNotO; "HTTP_STATUS_NOT_OK"
0x18002645c  retn
0x18002645d  lea     rax, aCustomLogging; "CUSTOM_LOGGING"
0x180026464  retn
0x180026465  cmp     ecx, 14h
0x180026468  ja      short loc_1800264C2
0x18002646a  jz      short loc_1800264BA
0x18002646c  sub     ecx, 0Eh
0x18002646f  jz      short loc_1800264B2
0x180026471  sub     ecx, 1
0x180026474  jz      short loc_1800264AA
0x180026476  sub     ecx, 1
0x180026479  jz      short loc_1800264A2
0x18002647b  sub     ecx, 1
0x18002647e  jz      short loc_18002649A
0x180026480  sub     ecx, 1
0x180026483  jz      short loc_180026492
0x180026485  cmp     ecx, 1
0x180026488  jnz     short loc_1800264DB
0x18002648a  lea     rax, aResponseSendin; "RESPONSE_SENDING_RAW_HEADERS"
0x180026491  retn
0x180026492  lea     rax, aFileNotCached; "FILE_NOT_CACHED"
0x180026499  retn
0x18002649a  lea     rax, aResponseMoreDa; "RESPONSE_MORE_DATA"
0x1800264a1  retn
0x1800264a2  lea     rax, aStaticRequestQ; "STATIC_REQUEST_QUERYSTRING"
0x1800264a9  retn
0x1800264aa  lea     rax, aIsapiNotCachin; "ISAPI_NOT_CACHING"
0x1800264b1  retn
0x1800264b2  lea     rax, aSslRestriction; "SSL_RESTRICTION"
0x1800264b9  retn
0x1800264ba  lea     rax, aDynamicCompres; "DYNAMIC_COMPRESSION_ENABLED"
0x1800264c1  retn
0x1800264c2  sub     ecx, 15h
0x1800264c5  jz      short loc_1800264FE
0x1800264c7  sub     ecx, 1
0x1800264ca  jz      short loc_1800264F6
0x1800264cc  sub     ecx, 1
0x1800264cf  jz      short loc_1800264EE
0x1800264d1  sub     ecx, 1
0x1800264d4  jz      short loc_1800264E6
0x1800264d6  cmp     ecx, 1
0x1800264d9  jz      short loc_1800264DE
0x1800264db  xor     eax, eax
0x1800264dd  retn
0x1800264de  lea     rax, aRequestFilterR; "REQUEST_FILTER_RULE"
0x1800264e5  retn
0x1800264e6  lea     rax, aHandlerChanged; "HANDLER_CHANGED"
0x1800264ed  retn
0x1800264ee  lea     rax, aNoCacheInvalid; "NO_CACHE_INVALIDATOR"
0x1800264f5  retn
0x1800264f6  lea     rax, aVerbNotGet; "VERB_NOT_GET"
0x1800264fd  retn
0x1800264fe  lea     rax, aNoPipelineEnab; "NO_PIPELINE_ENABLE"
0x180026505  retn
```
