# CloudAPHelper::Initialize(_GUID const &)

- ea: `0x18005279c`
- end: `0x180052b2d`
- name: `?Initialize@CloudAPHelper@@QEAAJAEBU_GUID@@@Z`
- size: `913`
- prototype: `int(CloudAPHelper *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180093c00`

## callees

- `0x180001aa0`
- `0x180005090`
- `0x18005279c`
- `0x180078c20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180052855`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180052855`
- `SspiCli!LsaConnectUntrusted` at `0x18005297f`
- `SspiCli!LsaConnectUntrusted` at `0x18005297f`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800529c9`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180052a58`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800529c9`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180052a58`

## string_xrefs

- `0x1800528a5`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180052aaa`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18005295d`: `StringCchCopyN(m_wszCorrelationId) failed`

## pseudocode

```c

```
