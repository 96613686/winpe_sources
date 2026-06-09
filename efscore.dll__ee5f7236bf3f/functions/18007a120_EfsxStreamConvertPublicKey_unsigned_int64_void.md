# EfsxStreamConvertPublicKey(unsigned __int64,void * *)

- ea: `0x18007a120`
- end: `0x18007a50e`
- name: `?EfsxStreamConvertPublicKey@@YAK_KPEAPEAX@Z`
- size: `1006`
- prototype: `unsigned int __fastcall(NCRYPT_KEY_HANDLE hKey, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180080224`

## callees

- `0x180063698`
- `0x18007a120`
- `0x1800d87ac`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18007a4eb`
- `ncrypt!NCryptFreeObject` at `0x18007a4eb`
- `ncrypt!NCryptExportKey` at `0x18007a33d`
- `ncrypt!NCryptExportKey` at `0x18007a421`
- `ncrypt!NCryptExportKey` at `0x18007a33d`
- `ncrypt!NCryptExportKey` at `0x18007a421`
- `ncrypt!NCryptGetProperty` at `0x18007a17f`
- `ncrypt!NCryptGetProperty` at `0x18007a1d2`
- `ncrypt!NCryptGetProperty` at `0x18007a2cb`
- `ncrypt!NCryptGetProperty` at `0x18007a17f`
- `ncrypt!NCryptGetProperty` at `0x18007a1d2`
- `ncrypt!NCryptGetProperty` at `0x18007a2cb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007a4bf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007a4bf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007a2f5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007a2f5`
- `bcrypt!BCryptDestroyKey` at `0x18007a491`
- `bcrypt!BCryptDestroyKey` at `0x18007a491`
- `bcrypt!BCryptImportKeyPair` at `0x18007a45c`
- `bcrypt!BCryptImportKeyPair` at `0x18007a45c`
- `ntdll!RtlNtStatusToDosError` at `0x18007a301`
- `ntdll!RtlNtStatusToDosError` at `0x18007a468`
- `ntdll!RtlNtStatusToDosError` at `0x18007a301`
- `ntdll!RtlNtStatusToDosError` at `0x18007a468`

## pseudocode

```c

```
