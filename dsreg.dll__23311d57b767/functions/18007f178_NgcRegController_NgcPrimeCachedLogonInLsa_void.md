# NgcRegController::NgcPrimeCachedLogonInLsa(void)

- ea: `0x18007f178`
- end: `0x18007f38d`
- name: `?NgcPrimeCachedLogonInLsa@NgcRegController@@SAJXZ`
- size: `533`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007e020`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18000db10`
- `0x180031a78`
- `0x180042628`
- `0x18007f178`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18007f351`
- `SspiCli!LsaFreeReturnBuffer` at `0x18007f351`
- `SspiCli!LsaConnectUntrusted` at `0x18007f251`
- `SspiCli!LsaConnectUntrusted` at `0x18007f251`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18007f32c`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18007f32c`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18007f2e4`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18007f2e4`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18007f28c`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18007f28c`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18007f215`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18007f215`

## string_xrefs

- `0x18007f1d8`: `NgcRegController::NgcPrimeCachedLogonInLsa`

## pseudocode

```c

```
