# LPA::Lpd::DownloadInstance::DecodeX509ExtensionValue(char const *,uchar const *,ulong,ulong,void * *,ulong &)

- ea: `0x1800adc0c`
- end: `0x1800adc84`
- name: `?DecodeX509ExtensionValue@DownloadInstance@Lpd@LPA@@CAJPEBDPEBEKKPEAPEAXAEAK@Z`
- size: `120`
- prototype: `__int64 __usercall@<rax>(LPCSTR lpszStructType@<rcx>, BYTE *pbEncoded@<rdx>, DWORD cbEncoded@<r8d>, unsigned int@<r9d>, void **, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b062c`
- `0x1800b8840`
- `0x1800b926c`

## callees

- `0x1800adc0c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800adc65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800adc65`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800adc48`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800adc48`

## pseudocode

```c

```
