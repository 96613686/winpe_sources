# Microsoft::Diagnostics::XmlFileSignatureVerifier::ValidateCertificateChain(_CERT_CONTEXT const &,void *,_FILETIME)

- ea: `0x18011859c`
- end: `0x180118714`
- name: `?ValidateCertificateChain@XmlFileSignatureVerifier@Diagnostics@Microsoft@@CAJAEBU_CERT_CONTEXT@@PEAXU_FILETIME@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, HCERTSTORE hAdditionalStore, struct _FILETIME)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801179ec`

## callees

- `0x180064e6c`
- `0x180064e8c`
- `0x18011859c`
- `0x1801dda14`

## import_xrefs

- `CRYPT32!CertFreeCertificateChain` at `0x180118635`
- `CRYPT32!CertFreeCertificateChain` at `0x1801186fb`
- `CRYPT32!CertFreeCertificateChain` at `0x180118635`
- `CRYPT32!CertFreeCertificateChain` at `0x1801186fb`
- `CRYPT32!CertGetCertificateChain` at `0x18011860d`
- `CRYPT32!CertGetCertificateChain` at `0x18011860d`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180118673`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1801186a0`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180118673`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1801186a0`

## string_xrefs

- `0x18011861e`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x1801186ae`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x1801186d0`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`

## pseudocode

```c

```
