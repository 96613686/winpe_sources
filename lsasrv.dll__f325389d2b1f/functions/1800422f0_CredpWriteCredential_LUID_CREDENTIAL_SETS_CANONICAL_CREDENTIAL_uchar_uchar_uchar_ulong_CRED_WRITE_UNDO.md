# CredpWriteCredential(_LUID *,_CREDENTIAL_SETS *,_CANONICAL_CREDENTIAL * *,uchar,uchar,uchar,ulong,_CRED_WRITE_UNDO * *)

- ea: `0x1800422f0`
- end: `0x1800432af`
- name: `?CredpWriteCredential@@YAJPEAU_LUID@@PEAU_CREDENTIAL_SETS@@PEAPEAU_CANONICAL_CREDENTIAL@@EEEKPEAPEAU_CRED_WRITE_UNDO@@@Z`
- size: `4031`
- prototype: `__int64 __fastcall(struct _LUID *, struct _CREDENTIAL_SETS *, struct _CANONICAL_CREDENTIAL **, char, unsigned __int8, unsigned __int8, char, struct _CRED_WRITE_UNDO **)`
- caller_count: `6`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x1800419c0`
- `0x180041fd0`
- `0x1800c2814`
- `0x1800c35f4`
- `0x1800c61a0`
- `0x1800c6518`

## callees

- `0x18000c300`
- `0x180011278`
- `0x1800284d4`
- `0x18003a848`
- `0x18003bb50`
- `0x1800422f0`
- `0x1800442d0`
- `0x18007d674`
- `0x18008d1a8`
- `0x18008e360`
- `0x180096434`
- `0x180097c3c`
- `0x180097d88`
- `0x1800ada18`
- `0x1800b9304`
- `0x1800c3b00`
- `0x1800c5138`
- `0x1800c51e8`
- `0x1800c6518`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800427e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800427e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180042b5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180042b5b`
- `ntdll!RtlFreeHeap` at `0x180042712`
- `ntdll!RtlFreeHeap` at `0x180042712`
- `ntdll!RtlAllocateHeap` at `0x1800423c5`
- `ntdll!RtlAllocateHeap` at `0x1800423c5`
- `ntdll!RtlEqualUnicodeString` at `0x180042490`
- `ntdll!RtlEqualUnicodeString` at `0x1800424b9`
- `ntdll!RtlEqualUnicodeString` at `0x180042e81`
- `ntdll!RtlEqualUnicodeString` at `0x180042ea3`
- `ntdll!RtlEqualUnicodeString` at `0x180042490`
- `ntdll!RtlEqualUnicodeString` at `0x1800424b9`
- `ntdll!RtlEqualUnicodeString` at `0x180042e81`
- `ntdll!RtlEqualUnicodeString` at `0x180042ea3`
- `CRYPT32!CertFreeCertificateContext` at `0x18004327a`
- `CRYPT32!CertFreeCertificateContext` at `0x18004327a`
- `ncrypt!NCryptFreeObject` at `0x18004324d`
- `ncrypt!NCryptFreeObject` at `0x18004324d`
- `CRYPTSP!CryptReleaseContext` at `0x180043269`
- `CRYPTSP!CryptReleaseContext` at `0x180043269`

## pseudocode

```c

```
