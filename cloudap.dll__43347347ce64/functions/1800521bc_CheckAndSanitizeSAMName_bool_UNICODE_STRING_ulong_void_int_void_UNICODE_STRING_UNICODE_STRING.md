# CheckAndSanitizeSAMName(bool,_UNICODE_STRING *,ulong,void *,int (*)(void *,_UNICODE_STRING *),_UNICODE_STRING *)

- ea: `0x1800521bc`
- end: `0x180052280`
- name: `?CheckAndSanitizeSAMName@@YAJ_NPEAU_UNICODE_STRING@@KPEAXP6AH21@Z1@Z`
- size: `196`
- prototype: `__int64 __fastcall(char, struct _UNICODE_STRING *, unsigned int, void *, int (*)(void *, struct _UNICODE_STRING *), struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180056684`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800521bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswascii` at `0x1800521e7`
- `api-ms-win-crt-private-l1-1-0!_o_iswascii` at `0x1800521e7`
- `api-ms-win-crt-private-l1-1-0!_o_iswprint` at `0x1800521f9`
- `api-ms-win-crt-private-l1-1-0!_o_iswprint` at `0x1800521f9`
- `LSASRV!LsaISanitizeSAMName` at `0x18005226b`
- `LSASRV!LsaISanitizeSAMName` at `0x18005226b`

## string_xrefs

- `0x180052207`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`

## pseudocode

```c

```
