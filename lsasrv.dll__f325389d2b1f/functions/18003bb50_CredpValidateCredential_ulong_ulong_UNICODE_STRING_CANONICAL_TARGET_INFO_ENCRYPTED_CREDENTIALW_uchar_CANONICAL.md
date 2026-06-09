# CredpValidateCredential(ulong,ulong,_UNICODE_STRING *,_CANONICAL_TARGET_INFO *,_ENCRYPTED_CREDENTIALW *,uchar *,_CANONICAL_CREDENTIAL * *)

- ea: `0x18003bb50`
- end: `0x18003db6d`
- name: `?CredpValidateCredential@@YAJKKPEAU_UNICODE_STRING@@PEAU_CANONICAL_TARGET_INFO@@PEAU_ENCRYPTED_CREDENTIALW@@PEAEPEAPEAU_CANONICAL_CREDENTIAL@@@Z`
- size: `8221`
- prototype: `__int64 __fastcall(DWORD, int, HLOCAL *, const UNICODE_STRING *, struct _ENCRYPTED_CREDENTIALW *, unsigned __int8 *, struct _CANONICAL_CREDENTIAL **)`
- caller_count: `5`
- callee_count: `29`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a880`
- `0x1800419c0`
- `0x1800422f0`
- `0x1800c35f4`
- `0x1800c6518`

## callees

- `0x180009330`
- `0x18000c300`
- `0x180011278`
- `0x1800284d4`
- `0x18003b4b0`
- `0x18003ba7c`
- `0x18003bb50`
- `0x18003db80`
- `0x18003ee94`
- `0x180046984`
- `0x180078c14`
- `0x180088290`
- `0x18008e360`
- `0x180097138`
- `0x180097c3c`
- `0x180097f74`
- `0x18009829c`
- `0x1800988fc`
- `0x1800ada18`
- `0x1800af60c`
- `0x1800b01fc`
- `0x1800b02b8`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800c7ab0`
- `0x1800c7e28`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c72d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c7c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d785`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d81a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003db5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c72d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c7c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d785`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d81a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003db5c`
- `ntdll!RtlAllocateHeap` at `0x18003c24d`
- `ntdll!RtlAllocateHeap` at `0x18003c24d`
- `ntdll!RtlCopyUnicodeString` at `0x18003c452`
- `ntdll!RtlCopyUnicodeString` at `0x18003c452`
- `ntdll!RtlGetLastNtStatus` at `0x18003d51c`
- `ntdll!RtlGetLastNtStatus` at `0x18003d5b4`
- `ntdll!RtlGetLastNtStatus` at `0x18003d51c`
- `ntdll!RtlGetLastNtStatus` at `0x18003d5b4`
- `ntdll!RtlInitUnicodeString` at `0x18003c51b`
- `ntdll!RtlInitUnicodeString` at `0x18003ca18`
- `ntdll!RtlInitUnicodeString` at `0x18003c51b`
- `ntdll!RtlInitUnicodeString` at `0x18003ca18`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18003d00a`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18003d00a`
- `bcrypt!BCryptEncrypt` at `0x18003c14c`
- `bcrypt!BCryptEncrypt` at `0x18003c14c`
- `netutils!NetpIsDomainNameValid` at `0x18003c8e0`
- `netutils!NetpIsDomainNameValid` at `0x18003c8e0`
- `api-ms-win-security-credentials-l2-1-0!CredpDecodeCredential` at `0x18003ce8c`
- `api-ms-win-security-credentials-l2-1-0!CredpDecodeCredential` at `0x18003ce8c`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x18003d5a4`
- `api-ms-win-security-credentials-l2-1-1!CredUnprotectEx` at `0x18003d5a4`

## pseudocode

```c

```
