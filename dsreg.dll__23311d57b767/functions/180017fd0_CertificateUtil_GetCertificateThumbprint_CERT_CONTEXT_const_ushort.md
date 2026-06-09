# CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)

- ea: `0x180017fd0`
- end: `0x180018324`
- name: `?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `852`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x1800260a4`
- `0x1800264a8`
- `0x180031930`
- `0x180042c18`
- `0x18005c780`
- `0x18005c95c`
- `0x180096d08`

## callees

- `0x1800084f4`
- `0x18000cbd8`
- `0x180017fd0`
- `0x1800307c4`
- `0x18003334c`
- `0x180043ef8`
- `0x180044300`
- `0x18004654c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182d9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001804e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800182cb`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001804e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800182cb`

## string_xrefs

- `0x180018206`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x1800181ff`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c

```
