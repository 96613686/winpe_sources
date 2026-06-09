# GetDriverSignInfo(void *,ushort const *,void *,ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180053edc`
- end: `0x1800544e1`
- name: `?GetDriverSignInfo@@YAJPEAXPEBG0PEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@3@Z`
- size: `1541`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, unsigned __int16 *pvObject, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180015948`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180006eb8`
- `0x180006ec4`
- `0x180007014`
- `0x1800103e0`
- `0x1800538cc`
- `0x180053edc`
- `0x180055ef0`
- `0x180056804`
- `0x180056934`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800542c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800542e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800542c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800542e4`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18005400c`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18005400c`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18005412a`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18005426b`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18005412a`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18005426b`
- `WINTRUST!WinVerifyTrust` at `0x1800541ae`
- `WINTRUST!WinVerifyTrust` at `0x1800541ae`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x1800543f7`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x1800543f7`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18005417d`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18005417d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054016`
- `CRYPT32!CertFreeCertificateContext` at `0x180054230`
- `CRYPT32!CertFreeCertificateContext` at `0x180054230`

## string_xrefs

- `0x1800542d5`: `microsoft windows hardware compatibility publisher`

## pseudocode

```c

```
