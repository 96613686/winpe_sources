# IISCacheEvents::HTTPSYS_CACHEABLE::TranslateEnumReasonToString(IISCacheEvents::HTTPSYS_CACHEABLE::enumReason)

- ea: `0x1800283d8`
- end: `0x18002855c`
- name: `?TranslateEnumReasonToString@HTTPSYS_CACHEABLE@IISCacheEvents@@SAPEBGW4enumReason@12@@Z`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800276c8`

## callees

- `0x1800283d8`

## string_xrefs

- `0x18002842a`: `HTTPSYS_CACHE_DISABLED`
- `0x180028421`: `FILE_COMPRESSIBLE`
- `0x180028482`: `FILTER_CACHE_UNAWARE`
- `0x180028479`: `NON_ANONYMOUS_ACCESS`
- `0x1800284dd`: `FILE_NOT_CACHED`
- `0x18002850a`: `DYNAMIC_COMPRESSION_ENABLED`
- `0x180028542`: `NO_CACHE_INVALIDATOR`

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
0x1800283d8  cmp     ecx, 0Dh
0x1800283db  ja      loc_1800284AF
0x1800283e1  jz      loc_1800284A6
0x1800283e7  cmp     ecx, 6
0x1800283ea  ja      short loc_18002844E
0x1800283ec  jz      short loc_180028445
0x1800283ee  test    ecx, ecx
0x1800283f0  jz      short loc_18002843C
0x1800283f2  sub     ecx, 1
0x1800283f5  jz      short loc_180028433
0x1800283f7  sub     ecx, 1
0x1800283fa  jz      short loc_18002842A
0x1800283fc  sub     ecx, 1
0x1800283ff  jz      short loc_180028421
0x180028401  sub     ecx, 1
0x180028404  jz      short loc_180028418
0x180028406  cmp     ecx, 1
0x180028409  jnz     loc_18002852C
0x18002840f  lea     rax, aSupressingEnti; "SUPRESSING_ENTITY"
0x180028416  retn
0x180028418  lea     rax, aFooterEnabled; "FOOTER_ENABLED"
0x18002841f  retn
0x180028421  lea     rax, aFileCompressib; "FILE_COMPRESSIBLE"
0x180028428  retn
0x18002842a  lea     rax, aHttpsysCacheDi; "HTTPSYS_CACHE_DISABLED"
0x180028431  retn
0x180028433  lea     rax, aNoMetadata; "NO_METADATA"
0x18002843a  retn
0x18002843c  lea     rax, aOk_0; "OK"
0x180028443  retn
0x180028445  lea     rax, aUrlChangeByFil; "URL_CHANGE_BY_FILTER"
0x18002844c  retn
0x18002844e  sub     ecx, 7
0x180028451  jz      short loc_18002849D
0x180028453  sub     ecx, 1
0x180028456  jz      short loc_180028494
0x180028458  sub     ecx, 1
0x18002845b  jz      short loc_18002848B
0x18002845d  sub     ecx, 1
0x180028460  jz      short loc_180028482
0x180028462  sub     ecx, 1
0x180028465  jz      short loc_180028479
0x180028467  cmp     ecx, 1
0x18002846a  jnz     loc_18002852C
0x180028470  lea     rax, aIpRestrictionS; "IP_RESTRICTION_SET"
0x180028477  retn
0x180028479  lea     rax, aNonAnonymousAc; "NON_ANONYMOUS_ACCESS"
0x180028480  retn
0x180028482  lea     rax, aFilterCacheUna; "FILTER_CACHE_UNAWARE"
0x180028489  retn
0x18002848b  lea     rax, aHandlerHttpsys; "HANDLER_HTTPSYS_UNFRIENDLY"
0x180028492  retn
0x180028494  lea     rax, aChildRequest; "CHILD_REQUEST"
0x18002849b  retn
0x18002849d  lea     rax, aHttpStatusNotO; "HTTP_STATUS_NOT_OK"
0x1800284a4  retn
0x1800284a6  lea     rax, aCustomLogging; "CUSTOM_LOGGING"
0x1800284ad  retn
0x1800284af  cmp     ecx, 14h
0x1800284b2  ja      short loc_180028513
0x1800284b4  jz      short loc_18002850A
0x1800284b6  sub     ecx, 0Eh
0x1800284b9  jz      short loc_180028501
0x1800284bb  sub     ecx, 1
0x1800284be  jz      short loc_1800284F8
0x1800284c0  sub     ecx, 1
0x1800284c3  jz      short loc_1800284EF
0x1800284c5  sub     ecx, 1
0x1800284c8  jz      short loc_1800284E6
0x1800284ca  sub     ecx, 1
0x1800284cd  jz      short loc_1800284DD
0x1800284cf  cmp     ecx, 1
0x1800284d2  jnz     short loc_18002852C
0x1800284d4  lea     rax, aResponseSendin; "RESPONSE_SENDING_RAW_HEADERS"
0x1800284db  retn
0x1800284dd  lea     rax, aFileNotCached; "FILE_NOT_CACHED"
0x1800284e4  retn
0x1800284e6  lea     rax, aResponseMoreDa; "RESPONSE_MORE_DATA"
0x1800284ed  retn
0x1800284ef  lea     rax, aStaticRequestQ; "STATIC_REQUEST_QUERYSTRING"
0x1800284f6  retn
0x1800284f8  lea     rax, aIsapiNotCachin; "ISAPI_NOT_CACHING"
0x1800284ff  retn
0x180028501  lea     rax, aSslRestriction; "SSL_RESTRICTION"
0x180028508  retn
0x18002850a  lea     rax, aDynamicCompres; "DYNAMIC_COMPRESSION_ENABLED"
0x180028511  retn
0x180028513  sub     ecx, 15h
0x180028516  jz      short loc_180028554
0x180028518  sub     ecx, 1
0x18002851b  jz      short loc_18002854B
0x18002851d  sub     ecx, 1
0x180028520  jz      short loc_180028542
0x180028522  sub     ecx, 1
0x180028525  jz      short loc_180028539
0x180028527  cmp     ecx, 1
0x18002852a  jz      short loc_180028530
0x18002852c  xor     eax, eax
0x18002852e  retn
0x180028530  lea     rax, aRequestFilterR; "REQUEST_FILTER_RULE"
0x180028537  retn
0x180028539  lea     rax, aHandlerChanged; "HANDLER_CHANGED"
0x180028540  retn
0x180028542  lea     rax, aNoCacheInvalid; "NO_CACHE_INVALIDATOR"
0x180028549  retn
0x18002854b  lea     rax, aVerbNotGet; "VERB_NOT_GET"
0x180028552  retn
0x180028554  lea     rax, aNoPipelineEnab; "NO_PIPELINE_ENABLE"
0x18002855b  retn
```
