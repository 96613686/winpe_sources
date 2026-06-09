# CTsRdpCertSignature::Sign(void)

- ea: `0x1800fa790`
- end: `0x1800faee7`
- name: `?Sign@CTsRdpCertSignature@@UEAAJXZ`
- size: `1879`
- prototype: `__int64 __fastcall(CTsRdpCertSignature *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800fa790`
- `0x180129c38`
- `0x180129c50`
- `0x1801a2b68`
- `0x1801a2c38`
- `0x18048f2e8`
- `0x18048f5bc`
- `0x180688f3e`

## import_xrefs

- `msvcrt!wcstombs_s` at `0x1800faaff`
- `msvcrt!wcstombs_s` at `0x1800fabcf`
- `msvcrt!wcstombs_s` at `0x1800faaff`
- `msvcrt!wcstombs_s` at `0x1800fabcf`
- `KERNEL32!GetLastError` at `0x1800faca5`
- `KERNEL32!GetLastError` at `0x1800face2`
- `KERNEL32!GetLastError` at `0x1800fadb9`
- `KERNEL32!GetLastError` at `0x1800fadf6`
- `KERNEL32!GetLastError` at `0x1800faca5`
- `KERNEL32!GetLastError` at `0x1800face2`
- `KERNEL32!GetLastError` at `0x1800fadb9`
- `KERNEL32!GetLastError` at `0x1800fadf6`
- `KERNEL32!LocalAlloc` at `0x1800fad08`
- `KERNEL32!LocalAlloc` at `0x1800fad08`
- `KERNEL32!LocalFree` at `0x1800fae0e`
- `KERNEL32!LocalFree` at `0x1800fae0e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800fa973`
- `ADVAPI32!RegOpenKeyExW` at `0x1800fa973`
- `ADVAPI32!RegQueryValueExW` at `0x1800fa9a3`
- `ADVAPI32!RegQueryValueExW` at `0x1800faa31`
- `ADVAPI32!RegQueryValueExW` at `0x1800fa9a3`
- `ADVAPI32!RegQueryValueExW` at `0x1800faa31`
- `ADVAPI32!RegCloseKey` at `0x1800faecd`
- `ADVAPI32!RegCloseKey` at `0x1800faecd`
- `CRYPT32!CryptSignMessage` at `0x1800fac7c`
- `CRYPT32!CryptSignMessage` at `0x1800fad90`
- `CRYPT32!CryptSignMessage` at `0x1800fac7c`
- `CRYPT32!CryptSignMessage` at `0x1800fad90`
- `CRYPT32!CertFreeCertificateChain` at `0x1800fae46`
- `CRYPT32!CertFreeCertificateChain` at `0x1800fae46`

## string_xrefs

- `0x1800fa838`: `attempt to sign with invalid signer certificate`
- `0x1800fae9e`: `attempt to sign with missing certificate/data`
- `0x1800fa965`: `System\CurrentControlSet\Services\TScPubRPC`
- `0x1800faade`: `HashAlgorithm registry type is incorrect`

## pseudocode

```c

```
