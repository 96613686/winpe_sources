# EndpointDlp::Common::Certificate::GetStatus(std::vector<std::vector<uchar,std::allocator<uchar>>,std::allocator<std::vector<uchar,std::allocator<uchar>>>> const &,bool)

- ea: `0x180060ec8`
- end: `0x18006112d`
- name: `?GetStatus@Certificate@Common@EndpointDlp@@QEAA?AW4CertificateStatus@23@AEBV?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@_N@Z`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060ac8`

## callees

- `0x18000685c`
- `0x1800301a0`
- `0x180060ec8`
- `0x180061130`
- `0x180061188`
- `0x18010cb40`
- `0x1801f8780`
- `0x1801f880c`

## import_xrefs

- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180060fa3`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18006108f`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180060fa3`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18006108f`
- `CRYPT32!CertGetCertificateChain` at `0x180060f44`
- `CRYPT32!CertGetCertificateChain` at `0x180060f44`
- `CRYPT32!CertCloseStore` at `0x180061104`
- `CRYPT32!CertCloseStore` at `0x180061104`
- `CRYPT32!CertFreeCertificateChain` at `0x1800610f3`
- `CRYPT32!CertFreeCertificateChain` at `0x1800610f3`

## string_xrefs

- `0x180060f5d`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x180060fbc`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x1800610a8`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`

## pseudocode

```c

```
