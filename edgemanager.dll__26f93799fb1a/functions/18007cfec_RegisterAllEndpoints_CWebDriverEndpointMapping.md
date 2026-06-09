# RegisterAllEndpoints(CWebDriverEndpointMapping &)

- ea: `0x18007cfec`
- end: `0x18007e4ed`
- name: `?RegisterAllEndpoints@@YAXAEAVCWebDriverEndpointMapping@@@Z`
- size: `5377`
- prototype: `void __fastcall(struct CWebDriverEndpointMapping *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180065cd0`

## callees

- `0x18007b79c`
- `0x18007b87c`
- `0x18007b974`
- `0x18007ba7c`
- `0x18007bb90`
- `0x18007bc74`
- `0x18007bd70`
- `0x18007be90`
- `0x18007bf74`
- `0x18007c080`
- `0x18007c1a0`
- `0x18007c284`

## string_xrefs

- `0x18007d03e`: `DELETE`
- `0x18007d2d1`: `DELETE`
- `0x18007d323`: `DELETE`
- `0x18007d935`: `DELETE`
- `0x18007d994`: `DELETE`
- `0x18007dc35`: `DELETE`
- `0x18007dc69`: `DELETE`
- `0x18007df65`: `DELETE`
- `0x18007dfe7`: `DELETE`
- `0x18007e27d`: `DELETE`
- `0x18007d18d`: `application_cache`
- `0x18007dae4`: `cached_rendering_snapshot`
- `0x18007da6a`: `moveto`
- `0x18007da8c`: `_internal_getEdgeCPTempFolder`
- `0x18007db30`: `config`
- `0x18007dccb`: `processId`

## pseudocode

```c
void __fastcall RegisterAllEndpoints(struct CWebDriverEndpointMapping *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  int v6; // r9d
  int v7; // r9d
  int v8; // r9d
  int v9; // edx
  int v10; // r9d
  int v11; // edx
  int v12; // r9d
  int v13; // r9d
  int v14; // edx
  int v15; // r9d
  int v16; // edx
  int v17; // r9d
  int v18; // edx
  int v19; // r9d
  int v20; // edx
  int v21; // r9d
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-88h]
  int v33; // [rsp+20h] [rbp-88h]
  int v34; // [rsp+20h] [rbp-88h]
  int v35; // [rsp+20h] [rbp-88h]
  int v36; // [rsp+20h] [rbp-88h]
  int v37; // [rsp+20h] [rbp-88h]
  int v38; // [rsp+20h] [rbp-88h]
  int v39; // [rsp+20h] [rbp-88h]
  int v40; // [rsp+20h] [rbp-88h]

  CWebDriverEndpointMapping::Register<unsigned short const *>(a1, 2, 75, L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable>(a1, 1, 33, L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable>(a1, 2, 76, L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    0,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    0,
    144,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    0,
    145,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    0,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    17,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    31,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    81,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    31,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    81,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    32,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    64,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    3,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    4,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    121,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    v2,
    122,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    120,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    119,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    118,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    6,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    11,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    0,
    35,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    2,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    v3,
    10,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    v4,
    34,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    17,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    18,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    23,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    30,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    30,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    v5,
    16,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    (_DWORD)a1,
    2,
    38,
    v6,
    (unsigned int)L"session");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    5,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    7,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    (_DWORD)a1,
    2,
    36,
    v7,
    v32);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    66,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    24,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    26,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    67,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    (_DWORD)a1,
    1,
    20,
    v8,
    v33);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    39,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    40,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    (_DWORD)a1,
    v9,
    108,
    v10,
    v34);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    (_DWORD)a1,
    v11,
    115,
    v12,
    v35);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    43,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    0,
    106,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    (_DWORD)a1,
    0,
    149,
    v13,
    v36);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    0,
    41,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    0,
    42,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    44,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    69,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    91,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    79,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    25,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    21,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    22,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    21,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    22,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    65,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    92,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    93,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    1,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    47,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    68,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    46,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    9,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    80,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    12,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    49,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    84,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    1,
    13,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    1,
    48,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    50,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    45,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    83,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    70,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    51,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    74,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    107,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    2,
    105,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    129,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    117,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    109,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    113,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    114,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    111,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    (_DWORD)a1,
    v14,
    140,
    v15,
    v37);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    (_DWORD)a1,
    v16,
    139,
    v17,
    v38);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    2,
    137,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    2,
    138,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    110,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    146,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    116,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    112,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    141,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    130,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    2,
    128,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    147,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *>(
    (_DWORD)a1,
    v18,
    124,
    v19,
    v39);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *>(
    (_DWORD)a1,
    v20,
    125,
    v21,
    v40);
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v22,
    123,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v23,
    126,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v24,
    127,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v25,
    134,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v26,
    135,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v27,
    136,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v28,
    133,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v29,
    131,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    v30,
    132,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    52,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    85,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    77,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    95,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    v31,
    95,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    14,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    56,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    86,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    57,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    1,
    15,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *,enum WebDriverPathVariable>(
    a1,
    1,
    55,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    53,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    142,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    0,
    97,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    98,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    99,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    100,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    59,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    96,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    101,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    19,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    27,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    71,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    102,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    103,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    1,
    104,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    37,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    29,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    8,
    L"DELETE");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    94,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    2,
    60,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    61,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    143,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    148,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    72,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,unsigned short const *>(
    a1,
    0,
    73,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    72,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    62,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    87,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    63,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    88,
    L"POST");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    60,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *,enum WebDriverPathVariable,unsigned short const *>(
    a1,
    1,
    61,
    L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *>(a1, 1, 82, L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *>(a1, 1, 89, L"GET");
  CWebDriverEndpointMapping::Register<unsigned short const *>(a1, 2, 90, L"GET");
}

```

## disassembly

```asm
0x18007cfec  push    rbx
0x18007cfee  push    rbp
0x18007cfef  push    rsi
0x18007cff0  push    rdi
0x18007cff1  push    r12
0x18007cff3  push    r13
0x18007cff5  push    r14
0x18007cff7  push    r15
0x18007cff9  sub     rsp, 68h
0x18007cffd  mov     ebp, 2
0x18007d002  lea     rax, aSession; "session"
0x18007d009  lea     rsi, aPost; "POST"
0x18007d010  mov     qword ptr [rsp+0A8h+var_88], rax
0x18007d015  mov     r9, rsi
0x18007d018  mov     edx, ebp
0x18007d01a  mov     rbx, rcx
0x18007d01d  lea     r8d, [rbp+49h]
0x18007d021  call    ??$Register@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBG@Z; CWebDriverEndpointMapping::Register<ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const)
0x18007d026  lea     edi, [rbp-1]
0x18007d029  mov     rcx, rbx
0x18007d02c  mov     edx, edi
0x18007d02e  lea     r9, aGet; "GET"
0x18007d035  lea     r8d, [rbp+1Fh]
0x18007d039  call    ??$Register@PEBGW4WebDriverPathVariable@@@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable)
0x18007d03e  lea     r12, aDelete_0; "DELETE"
0x18007d045  mov     edx, ebp
0x18007d047  mov     r9, r12
0x18007d04a  lea     r8d, [rbp+4Ah]
0x18007d04e  mov     rcx, rbx
0x18007d051  call    ??$Register@PEBGW4WebDriverPathVariable@@@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable)
0x18007d056  lea     rax, aAcceptAlert; "accept_alert"
0x18007d05d  mov     r9, rsi
0x18007d060  xor     r8d, r8d
0x18007d063  mov     [rsp+0A8h+var_78], rax
0x18007d068  mov     edx, edi
0x18007d06a  mov     rcx, rbx
0x18007d06d  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d072  lea     r14, aActions; "actions"
0x18007d079  mov     r9, rsi
0x18007d07c  xor     edx, edx
0x18007d07e  mov     [rsp+0A8h+var_78], r14
0x18007d083  mov     r8d, 90h
0x18007d089  mov     rcx, rbx
0x18007d08c  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d091  mov     r9, r12
0x18007d094  mov     [rsp+0A8h+var_78], r14
0x18007d099  xor     edx, edx
0x18007d09b  mov     r8d, 91h
0x18007d0a1  mov     rcx, rbx
0x18007d0a4  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d0a9  lea     rax, aAccept; "accept"
0x18007d0b0  mov     r9, rsi
0x18007d0b3  mov     [rsp+0A8h+var_70], rax
0x18007d0b8  lea     rdi, aAlert; "alert"
0x18007d0bf  xor     r8d, r8d
0x18007d0c2  mov     [rsp+0A8h+var_78], rdi
0x18007d0c7  xor     edx, edx
0x18007d0c9  mov     rcx, rbx
0x18007d0cc  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGPEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@33@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,ushort const * const)
0x18007d0d1  lea     rax, aDismiss; "dismiss"
0x18007d0d8  mov     r9, rsi
0x18007d0db  mov     [rsp+0A8h+var_70], rax
0x18007d0e0  lea     r15d, [rbp+0Fh]
0x18007d0e4  mov     r8d, r15d
0x18007d0e7  mov     [rsp+0A8h+var_78], rdi
0x18007d0ec  xor     edx, edx
0x18007d0ee  mov     rcx, rbx
0x18007d0f1  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGPEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@33@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,ushort const * const)
0x18007d0f6  lea     r13, aText; "text"
0x18007d0fd  xor     edx, edx
0x18007d0ff  lea     ebp, [r15+0Eh]
0x18007d103  mov     [rsp+0A8h+var_70], r13
0x18007d108  mov     r8d, ebp
0x18007d10b  mov     [rsp+0A8h+var_78], rdi
0x18007d110  lea     r9, aGet; "GET"
0x18007d117  mov     rcx, rbx
0x18007d11a  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGPEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@33@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,ushort const * const)
0x18007d11f  mov     r9, rsi
0x18007d122  mov     [rsp+0A8h+var_70], r13
0x18007d127  lea     esi, [rbp+32h]
0x18007d12a  mov     [rsp+0A8h+var_78], rdi
0x18007d12f  mov     r8d, esi
0x18007d132  xor     edx, edx
0x18007d134  mov     rcx, rbx
0x18007d137  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGPEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@33@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,ushort const * const)
0x18007d13c  lea     rdi, aAlertText; "alert_text"
0x18007d143  mov     r8d, ebp
0x18007d146  mov     [rsp+0A8h+var_78], rdi
0x18007d14b  lea     ebp, [rsi-50h]
0x18007d14e  lea     r9, aGet; "GET"
0x18007d155  mov     edx, ebp
0x18007d157  mov     rcx, rbx
0x18007d15a  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d15f  lea     r9, aPost; "POST"
0x18007d166  mov     [rsp+0A8h+var_78], rdi
0x18007d16b  mov     r8d, esi
0x18007d16e  mov     edx, ebp
0x18007d170  mov     rcx, rbx
0x18007d173  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d178  lea     rax, aStatus; "status"
0x18007d17f  mov     edx, ebp
0x18007d181  mov     [rsp+0A8h+var_70], rax
0x18007d186  lea     r9, aGet; "GET"
0x18007d18d  lea     rax, aApplicationCac; "application_cache"
0x18007d194  mov     rcx, rbx
0x18007d197  lea     r8d, [r15+0Fh]
0x18007d19b  mov     [rsp+0A8h+var_78], rax
0x18007d1a0  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGPEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@33@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,ushort const * const)
0x18007d1a5  lea     rax, aBack; "back"
0x18007d1ac  mov     rcx, rbx
0x18007d1af  lea     rsi, aPost; "POST"
0x18007d1b6  mov     [rsp+0A8h+var_78], rax
0x18007d1bb  mov     r9, rsi
0x18007d1be  lea     edx, [rbp+1]
0x18007d1c1  lea     r8d, [r15+2Fh]
0x18007d1c5  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d1ca  lea     rax, aButtondown; "buttondown"
0x18007d1d1  mov     r9, rsi
0x18007d1d4  lea     r8d, [r15-0Eh]
0x18007d1d8  mov     [rsp+0A8h+var_78], rax
0x18007d1dd  mov     edx, ebp
0x18007d1df  mov     rcx, rbx
0x18007d1e2  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d1e7  lea     rax, aButtonup; "buttonup"
0x18007d1ee  mov     r9, rsi
0x18007d1f1  lea     r8d, [r15-0Dh]
0x18007d1f5  mov     [rsp+0A8h+var_78], rax
0x18007d1fa  mov     edx, ebp
0x18007d1fc  mov     rcx, rbx
0x18007d1ff  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d204  lea     ebp, [r15-0Fh]
0x18007d208  mov     r9, rsi
0x18007d20b  lea     rdi, aBrowserext; "browserext"
0x18007d212  mov     edx, ebp
0x18007d214  lea     r8d, [r15+68h]
0x18007d218  mov     [rsp+0A8h+var_78], rdi
0x18007d21d  mov     rcx, rbx
0x18007d220  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d225  mov     r9, r12
0x18007d228  mov     dword ptr [rsp+0A8h+var_70], ebp
0x18007d22c  lea     r8d, [r15+69h]
0x18007d230  mov     [rsp+0A8h+var_78], rdi
0x18007d235  mov     rcx, rbx
0x18007d238  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@34@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable)
0x18007d23d  lea     rax, aAction; "action"
0x18007d244  mov     r9, rsi
0x18007d247  mov     [rsp+0A8h+var_68], rax
0x18007d24c  lea     r8d, [r15+67h]
0x18007d250  mov     dword ptr [rsp+0A8h+var_70], ebp
0x18007d254  mov     edx, ebp
0x18007d256  mov     rcx, rbx
0x18007d259  mov     [rsp+0A8h+var_78], rdi
0x18007d25e  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@343@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d263  mov     [rsp+0A8h+var_68], r14
0x18007d268  lea     r8d, [r15+66h]
0x18007d26c  lea     r14, aGet; "GET"
0x18007d273  mov     dword ptr [rsp+0A8h+var_70], ebp
0x18007d277  mov     r9, r14
0x18007d27a  mov     [rsp+0A8h+var_78], rdi
0x18007d27f  mov     edx, ebp
0x18007d281  mov     rcx, rbx
0x18007d284  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@343@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d289  lea     rax, aBrowserexts; "browserexts"
0x18007d290  mov     r9, r14
0x18007d293  lea     r8d, [r15+65h]
0x18007d297  mov     [rsp+0A8h+var_78], rax
0x18007d29c  mov     edx, ebp
0x18007d29e  mov     rcx, rbx
0x18007d2a1  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d2a6  lea     r12, aClick; "click"
0x18007d2ad  mov     [rsp+0A8h+var_78], r12
0x18007d2b2  lea     ebp, [r15-0Bh]
0x18007d2b6  mov     r9, rsi
0x18007d2b9  mov     r8d, ebp
0x18007d2bc  lea     edx, [rbp-5]
0x18007d2bf  mov     rcx, rbx
0x18007d2c2  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d2c7  lea     rdi, aCookie; "cookie"
0x18007d2ce  mov     rcx, rbx
0x18007d2d1  lea     r9, aDelete_0; "DELETE"
0x18007d2d8  mov     [rsp+0A8h+var_78], rdi
0x18007d2dd  lea     edx, [rbp-4]
0x18007d2e0  lea     r8d, [r15-6]
0x18007d2e4  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d2e9  mov     r9, r14
0x18007d2ec  mov     [rsp+0A8h+var_78], rdi
0x18007d2f1  xor     edx, edx
0x18007d2f3  lea     r8d, [r15+12h]
0x18007d2f7  mov     rcx, rbx
0x18007d2fa  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d2ff  lea     eax, [rbp-4]
0x18007d302  mov     [rsp+0A8h+var_78], rdi
0x18007d307  mov     r8d, eax
0x18007d30a  mov     edx, eax
0x18007d30c  mov     r9, rsi
0x18007d30f  mov     rcx, rbx
0x18007d312  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d317  lea     r14d, [r15-0Ch]
0x18007d31b  mov     rcx, rbx
0x18007d31e  mov     dword ptr [rsp+0A8h+var_70], r14d
0x18007d323  lea     r9, aDelete_0; "DELETE"
0x18007d32a  lea     r8d, [r15-7]
0x18007d32e  mov     [rsp+0A8h+var_78], rdi
0x18007d333  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@34@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable)
0x18007d338  lea     r9, aGet; "GET"
0x18007d33f  mov     dword ptr [rsp+0A8h+var_70], r14d
0x18007d344  lea     r8d, [r15+11h]
0x18007d348  mov     [rsp+0A8h+var_78], rdi
0x18007d34d  mov     rcx, rbx
0x18007d350  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@34@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable)
0x18007d355  lea     rax, aDismissAlert; "dismiss_alert"
0x18007d35c  mov     r9, rsi
0x18007d35f  lea     edi, [rbp-5]
0x18007d362  mov     [rsp+0A8h+var_78], rax
0x18007d367  mov     edx, edi
0x18007d369  mov     r8d, r15d
0x18007d36c  mov     rcx, rbx
0x18007d36f  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d374  lea     rax, aDoubleclick; "doubleclick"
0x18007d37b  mov     r9, rsi
0x18007d37e  lea     r8d, [r15+1]
0x18007d382  mov     [rsp+0A8h+var_78], rax
0x18007d387  mov     edx, edi
0x18007d389  mov     rcx, rbx
0x18007d38c  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d391  lea     r15, aElement; "element"
0x18007d398  mov     r9, rsi
0x18007d39b  lea     edx, [rbp-4]
0x18007d39e  mov     [rsp+0A8h+var_78], r15
0x18007d3a3  lea     r8d, [rbp+11h]
0x18007d3a7  mov     rcx, rbx
0x18007d3aa  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d3af  lea     rsi, aActive; "active"
0x18007d3b6  mov     rcx, rbx
0x18007d3b9  lea     edi, [rbp+18h]
0x18007d3bc  mov     [rsp+0A8h+var_70], rsi
0x18007d3c1  mov     r8d, edi
0x18007d3c4  mov     [rsp+0A8h+var_78], r15
0x18007d3c9  lea     r9, aGet; "GET"
0x18007d3d0  lea     edx, [rbp-4]
0x18007d3d3  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGPEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@33@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,ushort const * const)
0x18007d3d8  mov     [rsp+0A8h+var_70], rsi
0x18007d3dd  lea     edx, [rbp-4]
0x18007d3e0  lea     rsi, aPost; "POST"
0x18007d3e7  mov     [rsp+0A8h+var_78], r15
0x18007d3ec  mov     r9, rsi
0x18007d3ef  mov     r8d, edi
0x18007d3f2  mov     rcx, rbx
0x18007d3f5  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGPEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@33@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,ushort const * const)
0x18007d3fa  lea     edi, [rbp-5]
0x18007d3fd  mov     dword ptr [rsp+0A8h+var_70], edi
0x18007d401  mov     [rsp+0A8h+var_78], r15
0x18007d406  lea     r9, aGet; "GET"
0x18007d40d  mov     rcx, rbx
0x18007d410  lea     r8d, [rbp+0Ah]
0x18007d414  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@34@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable)
0x18007d419  lea     rax, aAttribute; "attribute"
0x18007d420  mov     dword ptr [rsp+0A8h+var_60], r14d
0x18007d425  lea     edx, [rbp-4]
0x18007d428  mov     [rsp+0A8h+var_68], rax
0x18007d42d  lea     r8d, [rbp+20h]
0x18007d431  mov     rcx, rbx
0x18007d434  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@PEBGW41@@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3434@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable)
0x18007d439  lea     rax, aClear; "clear"
0x18007d440  mov     r9, rsi
0x18007d443  mov     [rsp+0A8h+var_68], rax
0x18007d448  lea     edx, [rbp-4]
0x18007d44b  mov     dword ptr [rsp+0A8h+var_70], edi
0x18007d44f  mov     r8d, r14d
0x18007d452  mov     rcx, rbx
0x18007d455  mov     [rsp+0A8h+var_78], r15
0x18007d45a  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@343@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d45f  mov     [rsp+0A8h+var_68], r12
0x18007d464  lea     r8d, [rbp+1]
0x18007d468  lea     r12d, [rbp-4]
0x18007d46c  mov     dword ptr [rsp+0A8h+var_70], edi
0x18007d470  mov     edx, r12d
0x18007d473  mov     [rsp+0A8h+var_78], r15
0x18007d478  mov     r9, rsi
0x18007d47b  mov     rcx, rbx
0x18007d47e  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@343@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d483  lea     rax, aCss; "css"
0x18007d48a  mov     dword ptr [rsp+0A8h+var_60], r14d
0x18007d48f  lea     r8d, [rbp+1Eh]
0x18007d493  mov     [rsp+0A8h+var_68], rax
0x18007d498  mov     edx, r12d
0x18007d49b  mov     rcx, rbx
0x18007d49e  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@PEBGW41@@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@3434@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable)
0x18007d4a3  lea     rax, aDisplayed; "displayed"
0x18007d4aa  mov     edx, edi
0x18007d4ac  mov     [rsp+0A8h+var_68], rax
0x18007d4b1  lea     r9, aGet; "GET"
0x18007d4b8  mov     dword ptr [rsp+0A8h+var_70], edi
0x18007d4bc  lea     r8d, [rbp+3Ch]
0x18007d4c0  mov     rcx, rbx
0x18007d4c3  mov     [rsp+0A8h+var_78], r15
0x18007d4c8  call    ??$Register@PEBGW4WebDriverPathVariable@@PEBGW41@PEBG@CWebDriverEndpointMapping@@QEAAXW4WebDriverSupportedProtocol@@W4WebDriverCommandCode@@PEBGQEBGW4WebDriverPathVariable@@343@Z; CWebDriverEndpointMapping::Register<ushort const *,WebDriverPathVariable,ushort const *,WebDriverPathVariable,ushort const *>(WebDriverSupportedProtocol,WebDriverCommandCode,ushort const *,ushort const * const,WebDriverPathVariable,ushort const * const,WebDriverPathVariable,ushort const * const)
0x18007d4cd  mov     [rsp+0A8h+var_68], r15
0x18007d4d2  lea     r8d, [rbp+12h]
0x18007d4d6  mov     dword ptr [rsp+0A8h+var_70], edi
  ... truncated ...
```
