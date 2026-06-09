# CallCloudAPPackage(ulong,uchar *,ulong *,void * *)

- ea: `0x1800d9c10`
- end: `0x1800d9dee`
- name: `?CallCloudAPPackage@@YAJKPEAEPEAKPEAPEAX@Z`
- size: `478`
- prototype: `int(unsigned int, unsigned __int8 *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800da278`

## callees

- `0x180011ce4`
- `0x1800d9c10`
- `0x1800dac88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d9d55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d9d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9d42`
- `ntdll!RtlInitString` at `0x1800d9d16`
- `ntdll!RtlInitString` at `0x1800d9d16`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800d9d28`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800d9d28`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800d9c98`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800d9cef`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800d9d4d`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800d9c98`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800d9cef`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800d9d4d`
- `SspiCli!LsaConnectUntrusted` at `0x1800d9cc9`
- `SspiCli!LsaConnectUntrusted` at `0x1800d9cc9`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800d9d8e`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1800d9d8e`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800d9ca7`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800d9cfe`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800d9dd2`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800d9ca7`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800d9cfe`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800d9dd2`

## string_xrefs

- `0x1800d9c7f`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c

```
