# CallCloudAPPackage(ulong,uchar *,ulong *,void * *)

- ea: `0x1800356f4`
- end: `0x1800358af`
- name: `?CallCloudAPPackage@@YAJKPEAEPEAKPEAPEAX@Z`
- size: `443`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800331d0`

## callees

- `0x1800343dc`
- `0x1800356f4`
- `0x18003a8a8`
- `0x18003bf28`
- `0x180040a3c`
- `0x180040a5c`

## import_xrefs

- `SspiCli!LsaDeregisterLogonProcess` at `0x18003580d`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18003580d`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800357cd`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800357cd`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18003584e`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18003584e`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800357fa`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800357fa`
- `SspiCli!LsaConnectUntrusted` at `0x180035787`
- `SspiCli!LsaConnectUntrusted` at `0x180035787`
- `ntdll!RtlInitString` at `0x1800357bb`
- `ntdll!RtlInitString` at `0x1800357bb`

## string_xrefs

- `0x18003575c`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18003579d`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800357db`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c

```
