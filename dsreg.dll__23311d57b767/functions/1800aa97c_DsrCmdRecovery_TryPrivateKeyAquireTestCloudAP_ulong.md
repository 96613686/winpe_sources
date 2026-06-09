# DsrCmdRecovery::TryPrivateKeyAquireTestCloudAP(ulong &)

- ea: `0x1800aa97c`
- end: `0x1800aacc9`
- name: `?TryPrivateKeyAquireTestCloudAP@DsrCmdRecovery@@SAJAEAK@Z`
- size: `845`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18002df9c`
- `0x1800a81f0`

## callees

- `0x1800084f4`
- `0x180012c7c`
- `0x1800296d4`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800aa97c`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x1800aac96`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800aac96`
- `SspiCli!LsaConnectUntrusted` at `0x1800aa9f9`
- `SspiCli!LsaConnectUntrusted` at `0x1800aa9f9`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800aaca5`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800aaca5`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800aab28`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800aab28`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800aaaa1`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800aaaa1`

## string_xrefs

- `0x1800aab90`: `%s: CloudAp Plugin response JSON parsing returned error code 0x%08x.\n`

## pseudocode

```c

```
