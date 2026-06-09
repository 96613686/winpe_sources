# CHttpBase::GetServerAndObjectPath(ushort const *,ushort * *,ushort * *,int *,ushort *)

- ea: `0x180045980`
- end: `0x180045c71`
- name: `?GetServerAndObjectPath@CHttpBase@@AEAAJPEBGPEAPEAG1PEAHPEAG@Z`
- size: `753`
- prototype: `int(CHttpBase *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, int *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180044088`
- `0x180046184`
- `0x180046938`

## callees

- `0x180001284`
- `0x180001290`
- `0x180015438`
- `0x1800172d4`
- `0x180045980`
- `0x18005bd72`

## import_xrefs

- `WINHTTP!WinHttpCrackUrl` at `0x180045a1e`
- `WINHTTP!WinHttpCrackUrl` at `0x180045a1e`
- `WININET!InternetCrackUrlW` at `0x180045a26`
- `WININET!InternetCrackUrlW` at `0x180045a26`

## pseudocode

```c

```
