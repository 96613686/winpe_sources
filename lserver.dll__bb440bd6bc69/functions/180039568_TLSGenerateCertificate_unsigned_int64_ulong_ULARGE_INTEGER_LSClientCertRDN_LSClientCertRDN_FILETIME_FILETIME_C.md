# TLSGenerateCertificate(unsigned __int64,ulong,_ULARGE_INTEGER *,__LSClientCertRDN *,__LSClientCertRDN *,_FILETIME *,_FILETIME *,_CERT_PUBLIC_KEY_INFO *,ulong,_CERT_EXTENSION *,ulong *,uchar * *)

- ea: `0x180039568`
- end: `0x1800397af`
- name: `?TLSGenerateCertificate@@YAK_KKPEAT_ULARGE_INTEGER@@PEAU__LSClientCertRDN@@2PEAU_FILETIME@@3PEAU_CERT_PUBLIC_KEY_INFO@@KPEAU_CERT_EXTENSION@@PEAKPEAPEAE@Z`
- size: `583`
- prototype: `unsigned int __usercall@<eax>(HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey@<rcx>, DWORD dwKeySpec@<edx>, union _ULARGE_INTEGER *@<r8>, struct __LSClientCertRDN *@<r9>, struct __LSClientCertRDN *, struct _FILETIME *, struct _FILETIME *, struct _CERT_PUBLIC_KEY_INFO *, unsigned int, struct _CERT_EXTENSION *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800397b8`
- `0x18003a1f8`

## callees

- `0x180005665`
- `0x180022910`
- `0x180039400`
- `0x180039568`
- `0x180039bb4`
- `0x18003a6a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003974d`
- `KERNEL32!LocalFree` at `0x180039769`
- `KERNEL32!LocalFree` at `0x180039784`
- `KERNEL32!LocalFree` at `0x18003974d`
- `KERNEL32!LocalFree` at `0x180039769`
- `KERNEL32!LocalFree` at `0x180039784`

## pseudocode

```c

```
