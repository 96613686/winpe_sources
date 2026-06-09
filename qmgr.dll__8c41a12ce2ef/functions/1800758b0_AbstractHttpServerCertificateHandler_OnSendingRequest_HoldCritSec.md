# AbstractHttpServerCertificateHandler::OnSendingRequest(HoldCritSec &)

- ea: `0x1800758b0`
- end: `0x180075c49`
- name: `?OnSendingRequest@AbstractHttpServerCertificateHandler@@MEAAXAEAVHoldCritSec@@@Z`
- size: `921`
- prototype: `void __fastcall(AbstractHttpServerCertificateHandler *__hidden this, struct HoldCritSec *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180033420`
- `0x180033480`
- `0x180034170`
- `0x1800758b0`
- `0x180080430`
- `0x18009b668`
- `0x18009d024`
- `0x1800bb4b8`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075a93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007599c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007599c`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180075aa8`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180075aa8`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180075b2c`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180075b2c`
- `CRYPT32!CertFreeCertificateContext` at `0x18007595f`
- `CRYPT32!CertFreeCertificateContext` at `0x18007595f`

## pseudocode

```c

```
