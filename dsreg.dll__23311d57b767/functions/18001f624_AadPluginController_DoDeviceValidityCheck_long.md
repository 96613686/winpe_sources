# AadPluginController::DoDeviceValidityCheck(long &)

- ea: `0x18001f624`
- end: `0x18001f83c`
- name: `?DoDeviceValidityCheck@AadPluginController@@SAJAEAJ@Z`
- size: `536`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002df9c`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180016c0c`
- `0x18001f624`
- `0x18002ba70`
- `0x180031a78`
- `0x1800420f0`
- `0x180042628`
- `0x18004c490`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18001f7c3`
- `SspiCli!LsaFreeReturnBuffer` at `0x18001f7c3`
- `SspiCli!LsaConnectUntrusted` at `0x18001f69a`
- `SspiCli!LsaConnectUntrusted` at `0x18001f69a`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18001f7e8`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18001f7e8`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18001f756`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18001f756`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18001f6d6`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18001f6d6`

## string_xrefs

- `0x18001f66e`: `AadPluginController::DoDeviceValidityCheck`

## pseudocode

```c

```
