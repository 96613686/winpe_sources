# CTSScpRegister::GetMachinesWithInstalledRoles(ushort const *,ulong *,ushort * * *)

- ea: `0x18007a050`
- end: `0x18007a53d`
- name: `?GetMachinesWithInstalledRoles@CTSScpRegister@@UEAAJPEBGPEAKPEAPEAPEAG@Z`
- size: `1261`
- prototype: `__int64 __fastcall(CTSScpRegister *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002d26`
- `0x180005665`
- `0x18000cf54`
- `0x18001ad74`
- `0x18001ae3c`
- `0x18001aea4`
- `0x180078f54`
- `0x180079740`
- `0x180079b58`
- `0x18007a050`
- `0x18007a544`
- `0x1800a0fb0`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18007a0c3`
- `ole32!CoInitializeEx` at `0x18007a0c3`
- `ole32!CoUninitialize` at `0x18007a504`
- `ole32!CoUninitialize` at `0x18007a504`
- `ACTIVEDS!__imp_ADsGetLastError` at `0x18007a354`
- `ACTIVEDS!__imp_ADsGetLastError` at `0x18007a354`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18007a288`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18007a2f7`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18007a288`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18007a2f7`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18007a4df`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18007a4df`
- `KERNEL32!LocalAlloc` at `0x18007a433`
- `KERNEL32!LocalAlloc` at `0x18007a433`
- `KERNEL32!LocalFree` at `0x18007a310`
- `KERNEL32!LocalFree` at `0x18007a4f3`
- `KERNEL32!LocalFree` at `0x18007a310`
- `KERNEL32!LocalFree` at `0x18007a4f3`

## string_xrefs

- `0x18007a3c4`: `"ComposeString"`

## pseudocode

```c

```
