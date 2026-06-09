# SSL_SERVER_CERT::DetermineUseOfSSLHardwareAccelerator(void)

- ea: `0x180031058`
- end: `0x18003122f`
- name: `?DetermineUseOfSSLHardwareAccelerator@SSL_SERVER_CERT@@AEAAJXZ`
- size: `471`
- prototype: `__int64 __fastcall(SSL_SERVER_CERT *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180031238`

## callees

- `0x180001210`
- `0x180001250`
- `0x180031058`

## import_xrefs

- `msvcrt!_stricmp` at `0x180031178`
- `msvcrt!_stricmp` at `0x180031178`
- `KERNEL32!GetLastError` at `0x1800310aa`
- `KERNEL32!GetLastError` at `0x180031150`
- `KERNEL32!GetLastError` at `0x1800310aa`
- `KERNEL32!GetLastError` at `0x180031150`
- `ADVAPI32!CryptGetProvParam` at `0x1800310e4`
- `ADVAPI32!CryptGetProvParam` at `0x180031110`
- `ADVAPI32!CryptGetProvParam` at `0x180031146`
- `ADVAPI32!CryptGetProvParam` at `0x1800310e4`
- `ADVAPI32!CryptGetProvParam` at `0x180031110`
- `ADVAPI32!CryptGetProvParam` at `0x180031146`
- `ADVAPI32!RegOpenKeyExA` at `0x1800311a7`
- `ADVAPI32!RegOpenKeyExA` at `0x1800311a7`
- `ADVAPI32!RegQueryValueExA` at `0x1800311d9`
- `ADVAPI32!RegQueryValueExA` at `0x1800311d9`
- `ADVAPI32!RegCloseKey` at `0x1800311e9`
- `ADVAPI32!RegCloseKey` at `0x1800311e9`
- `ADVAPI32!CryptReleaseContext` at `0x180031213`
- `ADVAPI32!CryptReleaseContext` at `0x180031213`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800310a0`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800310a0`

## pseudocode

```c

```
