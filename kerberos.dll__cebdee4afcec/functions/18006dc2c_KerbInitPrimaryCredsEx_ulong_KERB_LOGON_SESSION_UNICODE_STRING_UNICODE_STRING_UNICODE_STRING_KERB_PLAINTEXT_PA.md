# KerbInitPrimaryCredsEx(ulong,_KERB_LOGON_SESSION *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_PLAINTEXT_PASSWORD *,uchar,_CERT_CONTEXT const *,_KERB_MESSAGE_BUFFER *,ulong,_KERB_PRIMARY_CREDENTIAL * *)

- ea: `0x18006dc2c`
- end: `0x18006e330`
- name: `?KerbInitPrimaryCredsEx@@YAJKPEAU_KERB_LOGON_SESSION@@PEAU_UNICODE_STRING@@11PEAU_KERB_PLAINTEXT_PASSWORD@@EPEBU_CERT_CONTEXT@@PEAU_KERB_MESSAGE_BUFFER@@KPEAPEAU_KERB_PRIMARY_CREDENTIAL@@@Z`
- size: `1796`
- prototype: `int(unsigned int, struct _KERB_LOGON_SESSION *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _KERB_PLAINTEXT_PASSWORD *, unsigned __int8, const struct _CERT_CONTEXT *, struct _KERB_MESSAGE_BUFFER *, unsigned int, struct _KERB_PRIMARY_CREDENTIAL **)`
- caller_count: `6`
- callee_count: `27`
- tags: `loader_planting`

## callers

- `0x180006f04`
- `0x18007dd94`
- `0x18008ec88`
- `0x18008f53c`
- `0x1800adccc`
- `0x1800c48cc`

## callees

- `0x180008e18`
- `0x1800093f0`
- `0x18000b300`
- `0x180028ad0`
- `0x180029300`
- `0x18002b740`
- `0x18002cb68`
- `0x180032964`
- `0x180032f70`
- `0x180048824`
- `0x180060ce4`
- `0x18006517c`
- `0x180067cac`
- `0x18006ba6c`
- `0x18006d5dc`
- `0x18006dc2c`
- `0x18006e338`
- `0x18006e5d0`
- `0x18007108c`
- `0x18008ab80`
- `0x18008b70c`
- `0x18008e128`
- `0x18008e168`
- `0x1800af068`
- `0x1800c3ac4`
- `0x1800c419c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e2c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e2c0`
- `ntdll!RtlEqualUnicodeString` at `0x18006ddc3`
- `ntdll!RtlEqualUnicodeString` at `0x18006ddc3`
- `ntdll!RtlEnterCriticalSection` at `0x18006deec`
- `ntdll!RtlEnterCriticalSection` at `0x18006deec`
- `ntdll!RtlLeaveCriticalSection` at `0x18006de8c`
- `ntdll!RtlLeaveCriticalSection` at `0x18006de8c`
- `KerbClientShared!KerbClientDuplicateStoredCred` at `0x18006e066`
- `KerbClientShared!KerbClientDuplicateStoredCred` at `0x18006e094`
- `KerbClientShared!KerbClientDuplicateStoredCred` at `0x18006e066`
- `KerbClientShared!KerbClientDuplicateStoredCred` at `0x18006e094`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006e21e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006e21e`

## string_xrefs

- `0x18006ddd6`: `the caller failed access check %#x to init the GMSA credential: %#x\n`
- `0x18006df85`: `the caller failed access check %#x to init the GMSA credential from default creds: %#x\n`

## pseudocode

```c

```
