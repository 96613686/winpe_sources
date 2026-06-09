# AadPluginController::GetPrtAuthority(_AADPLUGIN_AUTHORITY_TYPE,_AADPLUGIN_PRT_INFO &)

- ea: `0x18004dd10`
- end: `0x18004df5c`
- name: `?GetPrtAuthority@AadPluginController@@SAJW4_AADPLUGIN_AUTHORITY_TYPE@@AEAU_AADPLUGIN_PRT_INFO@@@Z`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1800306e0`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180031a78`
- `0x180033404`
- `0x180038fdc`
- `0x1800420f0`
- `0x180042628`
- `0x18004c490`
- `0x18004dd10`
- `0x18004f260`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18004dee5`
- `SspiCli!LsaFreeReturnBuffer` at `0x18004dee5`
- `SspiCli!LsaConnectUntrusted` at `0x18004dd8f`
- `SspiCli!LsaConnectUntrusted` at `0x18004dd8f`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18004df0a`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18004df0a`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18004de49`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18004de49`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18004ddc9`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18004ddc9`

## string_xrefs

- `0x18004dd63`: `AadPluginController::GetPrtAuthority`

## pseudocode

```c

```
