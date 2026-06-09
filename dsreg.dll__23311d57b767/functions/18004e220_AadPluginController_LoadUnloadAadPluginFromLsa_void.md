# AadPluginController::LoadUnloadAadPluginFromLsa(void)

- ea: `0x18004e220`
- end: `0x18004e3c0`
- name: `?LoadUnloadAadPluginFromLsa@AadPluginController@@CAJXZ`
- size: `416`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180049f70`
- `0x18004eeb0`
- `0x18004f068`
- `0x180054738`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180031a78`
- `0x1800420f0`
- `0x180042628`
- `0x18004e220`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18004e361`
- `SspiCli!LsaFreeReturnBuffer` at `0x18004e361`
- `SspiCli!LsaConnectUntrusted` at `0x18004e269`
- `SspiCli!LsaConnectUntrusted` at `0x18004e269`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18004e386`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18004e386`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18004e305`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18004e305`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18004e2ac`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18004e2ac`

## string_xrefs

- `0x18004e26f`: `AadPluginController::LoadUnloadAadPluginFromLsa`
- `0x18004e31f`: `%s: LsaCallAuthenticationPackage(REINIT_PLUGINS) failed with NTSTATUS: 0x%08x; SUBSTATUS: 0x%08x.`
- `0x18004e332`: `CONNECTED_PROV_TRUSTED_CALLPACKAGE_REINIT_PLUGINS`

## pseudocode

```c

```
