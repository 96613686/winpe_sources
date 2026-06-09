# TLSCreateSelfSignCertificate

- ea: `0x18003a1f8`
- end: `0x18003a4ef`
- name: `TLSCreateSelfSignCertificate`
- size: `759`
- prototype: `__int64 __usercall@<rax>(HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey@<rcx>, DWORD dwKeySpec@<edx>, int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180021e48`
- `0x18002224c`
- `0x18007ccec`

## callees

- `0x180005665`
- `0x180022910`
- `0x180023030`
- `0x180039568`
- `0x18003a1f8`
- `0x18003a4f8`
- `0x1800a0fb0`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18003a306`
- `KERNEL32!GetSystemTime` at `0x18003a306`
- `KERNEL32!GetLastError` at `0x18003a32d`
- `KERNEL32!GetLastError` at `0x18003a32d`
- `KERNEL32!LocalFree` at `0x18003a4a5`
- `KERNEL32!LocalFree` at `0x18003a4a5`

## pseudocode

```c

```
