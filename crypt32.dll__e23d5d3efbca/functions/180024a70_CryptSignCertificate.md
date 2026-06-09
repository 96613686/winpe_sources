# CryptSignCertificate

- ea: `0x180024a70`
- end: `0x180024d2b`
- name: `CryptSignCertificate`
- size: `699`
- prototype: `BOOL __stdcall(HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey, DWORD dwKeySpec, DWORD dwCertEncodingType, const BYTE *pbEncodedToBeSigned, DWORD cbEncodedToBeSigned, PCRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm, const void *pvHashAuxInfo, BYTE *pbSignature, DWORD *pcbSignature)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180025120`
- `0x180071360`

## callees

- `0x180009da0`
- `0x180024a70`
- `0x180024d40`
- `0x180025cf0`
- `0x18003e1b0`
- `0x1800a9c1c`
- `0x1800ad02c`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024cba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024cba`
- `ncrypt!NCryptIsKeyHandle` at `0x180024ba2`
- `ncrypt!NCryptIsKeyHandle` at `0x180024ba2`
- `ncrypt!NCryptFreeObject` at `0x180024c23`
- `ncrypt!NCryptFreeObject` at `0x180024c23`
- `ncrypt!NCryptTranslateHandle` at `0x180024bcd`
- `ncrypt!NCryptTranslateHandle` at `0x180024bcd`
- `CRYPTSP!CryptHashData` at `0x180116a21`
- `CRYPTSP!CryptHashData` at `0x180116a21`
- `CRYPTSP!CryptDestroyHash` at `0x180024cf6`
- `CRYPTSP!CryptDestroyHash` at `0x180024cf6`
- `CRYPTSP!CryptSignHashA` at `0x180116a69`
- `CRYPTSP!CryptSignHashA` at `0x180116ae8`
- `CRYPTSP!CryptSignHashA` at `0x180116a69`
- `CRYPTSP!CryptSignHashA` at `0x180116ae8`
- `CRYPTSP!CryptCreateHash` at `0x180116a01`
- `CRYPTSP!CryptCreateHash` at `0x180116a01`

## pseudocode

```c

```
