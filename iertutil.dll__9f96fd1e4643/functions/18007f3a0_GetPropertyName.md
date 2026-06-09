# GetPropertyName

- ea: `0x18007f3a0`
- end: `0x18007f49b`
- name: `GetPropertyName`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18007f3a0`

## string_xrefs

- `0x18007f40b`: `Uri_PROPERTY_AUTHORITY`
- `0x18007f413`: `Uri_PROPERTY_ABSOLUTE_URI`
- `0x18007f3fb`: `Uri_PROPERTY_DOMAIN`
- `0x18007f403`: `Uri_PROPERTY_DISPLAY_URI`
- `0x18007f3eb`: `Uri_PROPERTY_FRAGMENT`
- `0x18007f3f3`: `Uri_PROPERTY_EXTENSION`
- `0x18007f3db`: `Uri_PROPERTY_PASSWORD`
- `0x18007f3e3`: `Uri_PROPERTY_HOST`
- `0x18007f41b`: `Uri_PROPERTY_PATH_AND_QUERY`
- `0x18007f3d3`: `Uri_PROPERTY_PATH`
- `0x18007f48b`: `Uri_PROPERTY_RAW_URI`
- `0x18007f493`: `Uri_PROPERTY_QUERY`
- `0x18007f47b`: `Uri_PROPERTY_USER_INFO`
- `0x18007f483`: `Uri_PROPERTY_SCHEME_NAME`
- `0x18007f46b`: `Uri_PROPERTY_HOST_TYPE`
- `0x18007f473`: `Uri_PROPERTY_USER_NAME`
- `0x18007f45b`: `Uri_PROPERTY_SCHEME`
- `0x18007f463`: `Uri_PROPERTY_PORT`
- `0x18007f453`: `Uri_PROPERTY_ZONE`

## pseudocode

```c
const wchar_t *__fastcall GetPropertyName(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx

  if ( a1 <= 9 )
  {
    if ( a1 == 9 )
      return L"Uri_PROPERTY_PATH_AND_QUERY";
    if ( !a1 )
      return L"Uri_PROPERTY_ABSOLUTE_URI";
    v1 = a1 - 1;
    if ( !v1 )
      return L"Uri_PROPERTY_AUTHORITY";
    v2 = v1 - 1;
    if ( !v2 )
      return L"Uri_PROPERTY_DISPLAY_URI";
    v3 = v2 - 1;
    if ( !v3 )
      return L"Uri_PROPERTY_DOMAIN";
    v4 = v3 - 1;
    if ( !v4 )
      return L"Uri_PROPERTY_EXTENSION";
    v5 = v4 - 1;
    if ( !v5 )
      return L"Uri_PROPERTY_FRAGMENT";
    v6 = v5 - 1;
    if ( !v6 )
      return L"Uri_PROPERTY_HOST";
    v7 = v6 - 1;
    if ( !v7 )
      return L"Uri_PROPERTY_PASSWORD";
    if ( v7 == 1 )
      return L"Uri_PROPERTY_PATH";
    return 0;
  }
  v9 = a1 - 10;
  if ( !v9 )
    return L"Uri_PROPERTY_QUERY";
  v10 = v9 - 1;
  if ( !v10 )
    return L"Uri_PROPERTY_RAW_URI";
  v11 = v10 - 1;
  if ( !v11 )
    return L"Uri_PROPERTY_SCHEME_NAME";
  v12 = v11 - 1;
  if ( !v12 )
    return L"Uri_PROPERTY_USER_INFO";
  v13 = v12 - 1;
  if ( !v13 )
    return L"Uri_PROPERTY_USER_NAME";
  v14 = v13 - 1;
  if ( !v14 )
    return L"Uri_PROPERTY_HOST_TYPE";
  v15 = v14 - 1;
  if ( !v15 )
    return L"Uri_PROPERTY_PORT";
  v16 = v15 - 1;
  if ( !v16 )
    return L"Uri_PROPERTY_SCHEME";
  if ( v16 != 1 )
    return 0;
  return L"Uri_PROPERTY_ZONE";
}

```

## disassembly

```asm
0x18007f3a0  cmp     ecx, 9
0x18007f3a3  jg      short loc_18007F423
0x18007f3a5  jz      short loc_18007F41B
0x18007f3a7  test    ecx, ecx
0x18007f3a9  jz      short loc_18007F413
0x18007f3ab  sub     ecx, 1
0x18007f3ae  jz      short loc_18007F40B
0x18007f3b0  sub     ecx, 1
0x18007f3b3  jz      short loc_18007F403
0x18007f3b5  sub     ecx, 1
0x18007f3b8  jz      short loc_18007F3FB
0x18007f3ba  sub     ecx, 1
0x18007f3bd  jz      short loc_18007F3F3
0x18007f3bf  sub     ecx, 1
0x18007f3c2  jz      short loc_18007F3EB
0x18007f3c4  sub     ecx, 1
0x18007f3c7  jz      short loc_18007F3E3
0x18007f3c9  sub     ecx, 1
0x18007f3cc  jz      short loc_18007F3DB
0x18007f3ce  cmp     ecx, 1
0x18007f3d1  jnz     short loc_18007F450
0x18007f3d3  lea     rax, aUriPropertyPat_0; "Uri_PROPERTY_PATH"
0x18007f3da  retn
0x18007f3db  lea     rax, aUriPropertyPas; "Uri_PROPERTY_PASSWORD"
0x18007f3e2  retn
0x18007f3e3  lea     rax, aUriPropertyHos_0; "Uri_PROPERTY_HOST"
0x18007f3ea  retn
0x18007f3eb  lea     rax, aUriPropertyFra; "Uri_PROPERTY_FRAGMENT"
0x18007f3f2  retn
0x18007f3f3  lea     rax, aUriPropertyExt; "Uri_PROPERTY_EXTENSION"
0x18007f3fa  retn
0x18007f3fb  lea     rax, aUriPropertyDom; "Uri_PROPERTY_DOMAIN"
0x18007f402  retn
0x18007f403  lea     rax, aUriPropertyDis; "Uri_PROPERTY_DISPLAY_URI"
0x18007f40a  retn
0x18007f40b  lea     rax, aUriPropertyAut; "Uri_PROPERTY_AUTHORITY"
0x18007f412  retn
0x18007f413  lea     rax, aUriPropertyAbs; "Uri_PROPERTY_ABSOLUTE_URI"
0x18007f41a  retn
0x18007f41b  lea     rax, aUriPropertyPat; "Uri_PROPERTY_PATH_AND_QUERY"
0x18007f422  retn
0x18007f423  sub     ecx, 0Ah
0x18007f426  jz      short loc_18007F493
0x18007f428  sub     ecx, 1
0x18007f42b  jz      short loc_18007F48B
0x18007f42d  sub     ecx, 1
0x18007f430  jz      short loc_18007F483
0x18007f432  sub     ecx, 1
0x18007f435  jz      short loc_18007F47B
0x18007f437  sub     ecx, 1
0x18007f43a  jz      short loc_18007F473
0x18007f43c  sub     ecx, 1
0x18007f43f  jz      short loc_18007F46B
0x18007f441  sub     ecx, 1
0x18007f444  jz      short loc_18007F463
0x18007f446  sub     ecx, 1
0x18007f449  jz      short loc_18007F45B
0x18007f44b  cmp     ecx, 1
0x18007f44e  jz      short loc_18007F453
0x18007f450  xor     eax, eax
0x18007f452  retn
0x18007f453  lea     rax, aUriPropertyZon; "Uri_PROPERTY_ZONE"
0x18007f45a  retn
0x18007f45b  lea     rax, aUriPropertySch_0; "Uri_PROPERTY_SCHEME"
0x18007f462  retn
0x18007f463  lea     rax, aUriPropertyPor; "Uri_PROPERTY_PORT"
0x18007f46a  retn
0x18007f46b  lea     rax, aUriPropertyHos; "Uri_PROPERTY_HOST_TYPE"
0x18007f472  retn
0x18007f473  lea     rax, aUriPropertyUse; "Uri_PROPERTY_USER_NAME"
0x18007f47a  retn
0x18007f47b  lea     rax, aUriPropertyUse_0; "Uri_PROPERTY_USER_INFO"
0x18007f482  retn
0x18007f483  lea     rax, aUriPropertySch; "Uri_PROPERTY_SCHEME_NAME"
0x18007f48a  retn
0x18007f48b  lea     rax, aUriPropertyRaw; "Uri_PROPERTY_RAW_URI"
0x18007f492  retn
0x18007f493  lea     rax, aUriPropertyQue; "Uri_PROPERTY_QUERY"
0x18007f49a  retn
```
