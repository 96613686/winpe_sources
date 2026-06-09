# NgcPinManagement::ValidateAadCert(ushort const *,bool *,bool *)

- ea: `0x1800bde90`
- end: `0x1800bdf4f`
- name: `?ValidateAadCert@NgcPinManagement@@YAJPEBGPEA_N1@Z`
- size: `191`
- prototype: `__int64 __fastcall(NgcPinManagement *__hidden this, const unsigned __int16 *, bool *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bbdd0`

## callees

- `0x180011ce4`
- `0x1800bde90`

## import_xrefs

- `CRYPT32!CertVerifySubjectCertificateContext` at `0x1800bdf19`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x1800bdf19`
- `CRYPT32!CertVerifyTimeValidity` at `0x1800bdef6`
- `CRYPT32!CertVerifyTimeValidity` at `0x1800bdef6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800bdee1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800bdf37`
- `CRYPT32!CertFreeCertificateContext` at `0x1800bdee1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800bdf37`
- `cryptngc!NgcGetUserIdKeyCertificate` at `0x1800bdeb2`
- `cryptngc!NgcGetUserIdKeyCertificate` at `0x1800bdeb2`

## string_xrefs

- `0x1800bdec3`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`

## pseudocode

```c

```
