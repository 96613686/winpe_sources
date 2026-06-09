# SSL_STREAM_CONTEXT::ProcessCloseNotifyFromClient(DATA_STREAM_BUFFER *,ulong *,DATA_STREAM_BUFFER *,int *)

- ea: `0x18002fabc`
- end: `0x18002fce6`
- name: `?ProcessCloseNotifyFromClient@SSL_STREAM_CONTEXT@@QEAAJPEAVDATA_STREAM_BUFFER@@PEAK0PEAH@Z`
- size: `554`
- prototype: `__int64 __fastcall(SSL_STREAM_CONTEXT *__hidden this, struct DATA_STREAM_BUFFER *, unsigned int *, struct DATA_STREAM_BUFFER *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002cd6c`

## callees

- `0x18002cb40`
- `0x18002cc14`
- `0x18002fabc`
- `0x180047003`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `Secur32!DeleteSecurityContext` at `0x18002fc76`
- `Secur32!DeleteSecurityContext` at `0x18002fc76`
- `Secur32!DecryptMessage` at `0x18002fb84`
- `Secur32!DecryptMessage` at `0x18002fbf8`
- `Secur32!DecryptMessage` at `0x18002fb84`
- `Secur32!DecryptMessage` at `0x18002fbf8`
- `Secur32!QueryContextAttributesW` at `0x18002fb13`
- `Secur32!QueryContextAttributesW` at `0x18002fb13`
- `CRYPT32!CertFreeCertificateContext` at `0x18002fc89`
- `CRYPT32!CertFreeCertificateContext` at `0x18002fc89`

## pseudocode

```c

```
