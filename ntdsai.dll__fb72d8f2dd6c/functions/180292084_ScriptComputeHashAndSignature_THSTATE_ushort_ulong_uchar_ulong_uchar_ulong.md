# ScriptComputeHashAndSignature(_THSTATE *,ushort *,ulong,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x180292084`
- end: `0x180292291`
- name: `?ScriptComputeHashAndSignature@@YAKPEAU_THSTATE@@PEAGKPEAPEAEPEAK23@Z`
- size: `525`
- prototype: `unsigned int(struct _THSTATE *, unsigned __int16 *, unsigned int, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180291560`

## callees

- `0x1800067d0`
- `0x180292084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029213d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029223a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029213d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029223a`
- `CRYPTSP!CryptGetHashParam` at `0x1802921f6`
- `CRYPTSP!CryptGetHashParam` at `0x180292230`
- `CRYPTSP!CryptGetHashParam` at `0x1802921f6`
- `CRYPTSP!CryptGetHashParam` at `0x180292230`
- `CRYPTSP!CryptDestroyHash` at `0x18029224c`
- `CRYPTSP!CryptDestroyHash` at `0x18029225f`
- `CRYPTSP!CryptDestroyHash` at `0x18046bb3d`
- `CRYPTSP!CryptDestroyHash` at `0x18046bb50`
- `CRYPTSP!CryptDestroyHash` at `0x18029224c`
- `CRYPTSP!CryptDestroyHash` at `0x18029225f`
- `CRYPTSP!CryptDestroyHash` at `0x18046bb3d`
- `CRYPTSP!CryptDestroyHash` at `0x18046bb50`
- `CRYPTSP!CryptHashData` at `0x1802921b3`
- `CRYPTSP!CryptHashData` at `0x180292213`
- `CRYPTSP!CryptHashData` at `0x1802921b3`
- `CRYPTSP!CryptHashData` at `0x180292213`
- `CRYPTSP!CryptCreateHash` at `0x180292193`
- `CRYPTSP!CryptCreateHash` at `0x180292193`
- `CRYPTSP!CryptAcquireContextA` at `0x180292133`
- `CRYPTSP!CryptAcquireContextA` at `0x180292168`
- `CRYPTSP!CryptAcquireContextA` at `0x180292133`
- `CRYPTSP!CryptAcquireContextA` at `0x180292168`
- `CRYPTSP!CryptDuplicateHash` at `0x1802921cf`
- `CRYPTSP!CryptDuplicateHash` at `0x1802921cf`
- `CRYPTSP!CryptReleaseContext` at `0x180292271`
- `CRYPTSP!CryptReleaseContext` at `0x18046bb62`
- `CRYPTSP!CryptReleaseContext` at `0x180292271`
- `CRYPTSP!CryptReleaseContext` at `0x18046bb62`

## pseudocode

```c

```
