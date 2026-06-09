# ResourceAccountController::SaveCertificate(ushort *,struct_dsreg_server_response *,int *)

- ea: `0x1800439d4`
- end: `0x180043ca3`
- name: `?SaveCertificate@ResourceAccountController@@AEAAJPEAGPEAUstruct_dsreg_server_response@@PEAH@Z`
- size: `719`
- prototype: `int(ResourceAccountController *__hidden this, unsigned __int16 *, struct struct_dsreg_server_response *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b6930`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18001b560`
- `0x180035390`
- `0x180040df8`
- `0x1800439d4`
- `0x180043e54`
- `0x180043ef8`
- `0x18008bacc`
- `0x180093f00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180043c10`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180043c10`
- `CRYPT32!CertFreeCertificateContext` at `0x180043b8c`
- `CRYPT32!CertFreeCertificateContext` at `0x180043c6d`
- `CRYPT32!CertFreeCertificateContext` at `0x180043b8c`
- `CRYPT32!CertFreeCertificateContext` at `0x180043c6d`

## string_xrefs

- `0x180043a85`: `StringCompare`
- `0x180043b5d`: `RegistrationCertHelper::InstallCertificate`

## pseudocode

```c

```
