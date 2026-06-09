# DsrCmdRefreshPrt::RefreshPrt(void)

- ea: `0x1800ab918`
- end: `0x1800abc05`
- name: `?RefreshPrt@DsrCmdRefreshPrt@@SAJXZ`
- size: `749`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18009b940`

## callees

- `0x1800084f4`
- `0x180012c7c`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800ab918`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x1800abbd5`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800abbd5`
- `SspiCli!LsaConnectUntrusted` at `0x1800ab966`
- `SspiCli!LsaConnectUntrusted` at `0x1800ab966`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800abbe4`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800abbe4`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800abad4`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800abad4`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800aba1c`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800aba1c`

## string_xrefs

- `0x1800abb0d`: `PRT refresh scheduled. Check AAD event logs for details.\n`
- `0x1800abb23`: `PRT refresh scheduled. Check AAD event logs for details.\n`

## pseudocode

```c

```
