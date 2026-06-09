# DsrCmdRefreshPrt::RefreshP2PCerts(void)

- ea: `0x1800ab4f0`
- end: `0x1800ab912`
- name: `?RefreshP2PCerts@DsrCmdRefreshPrt@@SAJXZ`
- size: `1058`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18009b940`

## callees

- `0x1800084f4`
- `0x180012c7c`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x180098940`
- `0x1800ab4f0`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x1800ab8d9`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800ab8d9`
- `SspiCli!LsaConnectUntrusted` at `0x1800ab5e5`
- `SspiCli!LsaConnectUntrusted` at `0x1800ab5e5`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800ab8e8`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800ab8e8`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800ab76f`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800ab76f`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800ab68a`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800ab68a`

## string_xrefs

- `0x1800ab7da`: `If device P2P and CA certificates need to be included in the refresh, re-run the command with elevation.\n`

## pseudocode

```c

```
